Deterministic Sensitivity Analysis
==================================

Package: heemod
---------------

### Maintained by

Kevin Zarca - <kevin.zarca@gmail.com> (
<https://cran.r-project.org/web/packages/heemod/heemod.pdf> and
<https://cran.r-project.org/web/packages/heemod/index.html>)

What does this package do?
--------------------------

For more information on the full package functionality – see “Markov
Models” page under “State Transition Models”. This page will focus on
the deterministic sensitivity functions within the heemod package. This
information is taken from the “Deterministic Sensitivity Analysis”
Vignette (2019-10-22):
<https://cran.r-project.org/web/packages/heemod/vignettes/f_sensitivity.html>
This functionality reruns your Markov models with specified values for
individual parameters.

How do I input my data to it/what inputs does it take?
------------------------------------------------------

Upper and lower values for the paramters are given to define\_dsa().

    library(heemod)

    ## Registered S3 method overwritten by 'pryr':
    ##   method      from
    ##   print.bytes Rcpp

    se <- define_dsa(
      rr, .4, .6,
      cost_zido, 1500, 3000,
      cost_lami, 1500, 3000,  
      dr, .04, .08
    )

& run the sensitivity analysis with run\_dsa(), using res\_mod is the
model created \[see
<https://cran.r-project.org/web/packages/heemod/heemod.pdf> for how this
would be structured\]

    # res_dsa <- run_dsa(
    #   model = res_mod,
    #   dsa = se
    # )
    # Note code is ## to allow for inclusion without defining e.g. res_mod within this section

What outputs do I get?
----------------------

Res\_dsa is the output given from the above function, the example given
in the vignette gives the following (cut down for space):

    ## A sensitivity analysis on 4 parameters.
    ## 
    ## Parameters:
    ##   -rr
    ##   -cost_zido
    ##   -cost_lami
    ##   -dr
    ## 
    ## Sensitivity analysis:
    ## 
    ##                        cost_health cost_drugs cost_total life_year
    ## mono, cost_lami = 1500 46725886    19279596   48417031    8463.387
    ## comb, cost_lami = 1500 71019861    53642502   79593035   14198.651
    ## mono, cost_lami = 3000 46725886    19279596   48417031    8463.387
    ## comb, cost_lami = 3000 71019861    74940478   93812382   14198.651
    ## mono, cost_zido = 1500 46725886    12695081   43363208    8463.387
    #The results of this can be then plotted into a tornado diagram using:
    # plot(res_dsa,
    #      strategy = "mono",
    #      result = "cost",
    #      type = "simple")

    # Although note that whatever you put under “strategy” and “result” is what would be plot, so in the above case it would be the different cost estimates for the mono strategy. If you want the different ICER values plotted this code would then be; 
    # plot(res_dsa,
    #      strategy = "comb",
    #      result = "icer",
    #      type = "difference",
    #      limits_by_bars = FALSE)

Other packages
--------------

See below info

Other helpful resources
-----------------------

Alternatively, if you write your model using a different package or
functions (i.e. not heemod). Turn that whole modelling process into a
function (see:
<https://www.dummies.com/programming/r/how-to-move-from-a-script-to-a-function-in-r/>)
…. that can then be run with different input values for your variables
you are performing your deterministic sensitivity analyses on. For
example;

    DSA.cost <-  function(LCI.x, HCI.x) {
      #  LCI.x and HCI.x  higher and upper bounds for variable altering (cost of intervention)
      DSA <- data.frame(c("low.x", "high.x"),0L)
      colnames(DSA) <- c("variable","ICER")
      DSA[1,2] <- analysis(c.ill, LCI.x)  
     # analysis is the functional version of your model c.ill  highlights the variable you are changing #and LCI.x is the value you are changing it to
      DSA[2,2] <- analysis(c.ill, HCI.x)
      return(DSA)
    }
