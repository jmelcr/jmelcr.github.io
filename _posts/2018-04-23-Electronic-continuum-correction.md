---
layout: post
title:  "Electronic Continuum correction (ECC): Implicit model of polarizability"
author: jmelcr
permalink: blog/ECC-post
---

When I use term *polarizability*, 
people often assume I mean *explicit polarizability*,
which can be modeled for example using 
polarizable dipoles with Thole damping or
[Drude particles](https://en.wikipedia.org/wiki/Drude_particle). 
However, there is a relatively recently developed theory,
which provides an *implicit* model of polarizability,
which we term Electronic Continuum Correction (ECC)
(references: [MD in electronic continuum (MDEC)](http://scitation.aip.org/content/aip/journal/jcp/130/8/10.1063/1.3060164) 
and a [follow-up paper](http://dx.doi.org/10.1021/ct9005807)).

ECC is an implicit model of electronic polarizability,
in which a system of individual polarizable particles is represented
with a fixed-charge equivalent system, 
which includes the effects of electronic polarization in a mean-field way.
It is sometimes incorrectly percieved as being represented with a *non-polarizable* system, 
but the opposite is true - it only takes the same form as classical non-polarizable empirical force fields. 
In practice, we also often call ECC the *charge-scaling* approach,
however, that is only a practical realization of
embedding all atoms into a dielectric continuum 
with a high-frequency dielectric constant of the electrons
(scaling charges with the inverse square root of the dielectric constant provides the same effect).
It is important to note that the value of the 
high frequency dielectric constant  
is around 2 for almost any biologically relevant environment.
This means that even interfaces like biological membranes do not contain discontinuities of the electronic continuum. 
Given that the  high frequency dielectric constant of water is 1.78$ (i.e., the square of the refraction index), 
the scaling factor for ions in water is roughly 0.75. 

ECC significantly improves the accuracy of simulations of solvated [ions](https://aip.scitation.org/doi/abs/10.1063/1.5006779), 
and it was recently shown by our group that ECC is crucial also for [phospholipids](https://pubs.acs.org/doi/10.1021/acs.jpcb.7b12510).

Simulations with *explicitly polarizable* models are generally considered to be costly for a practical use in biophysics. 
The ECC-models, however, are computatinally as cheap as any other fixed-charged model,
yet they are polarizable - *implicitly polarizable*. 

