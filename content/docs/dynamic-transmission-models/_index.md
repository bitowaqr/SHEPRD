Dynamic Transmission Models
===========================

Introduction
------------

Dynamic models are generally used for communicable diseases. Unlike
static models which assume that infection risk is constant, in dynamic
models the infection risk parameter is variable. These models can be
deterministic or stochastic, individual or cohort based.

See also:
<a href="https://www.ispor.org/docs/default-source/resources/outcomes-research-guidelines-index/dynamic_transmission_modeling-5.pdf?sfvrsn=86c71849_0" class="uri">https://www.ispor.org/docs/default-source/resources/outcomes-research-guidelines-index/dynamic_transmission_modeling-5.pdf?sfvrsn=86c71849_0</a>.

When might I use this?
----------------------

The key feature of these models is that risk of infection varies with
the number of infectious agents present over the time modelled. This
means that indirect effects, such as herd immunity due to mass
vaccination, are accounted for. Dynamic transmission models are useful
for examining interventions and their impact on pathogen ecology, as
well as exploring an intervention’s impact on transmission. For example,
these models can be used to assess the effect of: \* decreasing the
susceptible proportion of the population (e.g. through vaccination), \*
decreasing contact between individuals (e.g. via isolation measures), \*
reducing the duration of the infectious period (e.g. by delivering drug
interventions), \* reducing transmissibility of the pathogen (e.g. by
delivering drug interventions).

In particular, these models are commonly used to measure the impact of a
vaccine in a population, and to investigate the use of antivirals or
isolation measures in disease outbreaks. For example, dynamic
transmission models have been used to assess the potential malaria risk
to the UK
(<a href="https://www.ncbi.nlm.nih.gov/pmc/articles/PMC2845590/" class="uri">https://www.ncbi.nlm.nih.gov/pmc/articles/PMC2845590/</a>).

Building a dynamic transmission model often requires more than one
package. However packages for learning to build dynamic transmission
models, which may be useful to the beginner are available. An example is
described below.

Transmisison Model Packages:
============================

Package: DSAIDE
---------------

DSAIDE - Dynamical Systems Approach to Infectious Disease Epidemiology
(Ecology/Evolution)

### Maintained by

Andreas Handel
(<a href="mailto:ahandel@uga.edu" class="email">ahandel@uga.edu</a>)

URLs
----

<a href="https://CRAN.R-project.org/package=DSAIDE" class="uri">https://CRAN.R-project.org/package=DSAIDE</a>
<a href="https://ahgroup.github.io/DSAIDE" class="uri">https://ahgroup.github.io/DSAIDE</a>
<a href="https://github.com/ahgroup/DSAIDE" class="uri">https://github.com/ahgroup/DSAIDE</a>
<a href="https://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1005642" class="uri">https://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1005642</a>

What does this package do?
--------------------------

The package contains a set of models focused on infectious disease
epidemiology. Each model comes with documentation and instructions which
highlight important concepts in infectious disease epidemiology and
explain how models can be used to understand these concepts. All models
can be explored through a graphical user interface, with no reading or
writing of code required. However, the package is designed to help the
user to move to direct interaction with pre-written models and
modification of the underlying models.

How do I input my data to it/what inputs does it take?
------------------------------------------------------

Inputs will be information on the population and the infection that the
user wants to model, such as the number of people who will be
susceptible initially and the rate of recovery from the infection.

What outputs do I get?
----------------------

Outputs will be information on the progression of the infection in the
population, such as the total number of individuals infected over the
simulation, which can be used for calculation of the economic cost and
benefits associated with an intervention.

Sample code section
-------------------

A range of sample code sections are available at
<a href="https://ahgroup.github.io/DSAIDE" class="uri">https://ahgroup.github.io/DSAIDE</a>.

Other packages
--------------

There are a wide variety of other packages availables for learning to
build dynamic transmission models, as well as a variety of packages that
are commonly used by those more familiar with dynamic transmission
modelling. Examples that demonstrate the use of some of these packages
can be found on the EpiRecipies website
(<a href="http://epirecip.es/epicookbook/" class="uri">http://epirecip.es/epicookbook/</a>).

Other helpful resources
-----------------------

The EpiRecipies project
(<a href="http://epirecip.es/epicookbook/" class="uri">http://epirecip.es/epicookbook/</a>)
aims to collate mathematical models of infectious disease transmission,
with implementations in R, Python, and Julia. The website has a diverse
selection of examples including simple deterministic models using
ordinary differential equations, simple stochastic models, models with
time-varying parameters, spatial models and network models. There are
also examples of applications to specific disease systems.
