---
layout: post
title:  "Electronic Continuum correction (ECC): Implicit model of polarizability"
author: jmelcr
permalink: blog/ECC-post
---

*(PhD student, thinking...)*

Polarizable or non-polarizable. 

Do I need it for my simulation? 
Are the effects of the electronic polarization that improtant? 

*Maybe.*

But is it worth the usual slowdown,
when it seems that other researchers usually get away without it?

*Maybe that with this ECC, 
the slowness is not that dramatic...*

*(student reading a [paper](https://www.frontiersin.org/articles/10.3389/fmolb.2019.00143/full))*
*...  the effects of electronic polarization can also be included 
at zero additional computational cost compared to standard fixed-charge force fields 
using the electronic continuum correction, ...*

Let's give it a try!

<HR>

The term *polarizability*, 
is often automatically assumed to mean *explicit polarizability*. 
No wonders -
using explicit polarizable dipoles with Thole damping or
[Drude particles](https://en.wikipedia.org/wiki/Drude_particle)
is a very common way to account for electronic polarization. 
In addition to those methods, however, 
there is also a relatively recently developed theory,
which provides an *implicit* model of polarizability
termed [Electronic Continuum Correction (ECC)](https://pubs.acs.org/doi/10.1021/acs.jpclett.9b02652)
(references: [MD in electronic continuum (MDEC)](http://scitation.aip.org/content/aip/journal/jcp/130/8/10.1063/1.3060164) 
and [another paper](http://dx.doi.org/10.1021/ct9005807)).

ECC is an implicit model of electronic polarizability,
in which a system of polarizable particles is represented
with an equivalent system of particles with fixed charges
including the effects of electronic polarization *implicitly* in a mean-field way.
It is often incorrectly percieved as a *non-polarizable* system again, 
but the opposite is true - it only takes the same form as classical non-polarizable force fields
with the effects of the electronic polarization implicitly included in the modified electrostatic interactions. 
The relation between the *original* and the *new* set of charges 
is almost trivial - mere linear scaling with a certain factor smaller than one provides the effect. 
That is also the reason why ECC is often referred as [the *charge-scaling* approach](https://pubs.acs.org/doi/10.1021/acs.jpclett.9b02652).
For ECC, it is important to note that the value of the 
high frequency dielectric constant  
is around 2 for almost any biologically relevant environment.
This means that even interfaces like biological membranes do not contain discontinuities of the electronic continuum. 
Given that the  high frequency dielectric constant of water is 1.78 (i.e., the square of the refraction index), 
the scaling factor for ions in water is roughly 0.75. 

ECC significantly improves the accuracy of simulations of solvated [ions](https://aip.scitation.org/doi/abs/10.1063/1.5006779) 
(freely available [manuscript](http://jungwirth.uochb.cas.cz/assets/papers/paper294.pdf)), 
and it was recently shown by our group that ECC is crucial also for 
[proteins](https://pubs.acs.org/doi/10.1021/acs.jpcb.7b12097) and 
[phospholipids](https://jmelcr.github.io/ecc_lipids/). 
The research on the latter was largely driven by the [NMRlipids](http://nmrlipids.blogspot.com/) community,
which has found that all current classical force fields 
overestimate the affinity of cations to PC lipid bilayers 
in the recent [publication](https://pubs.rsc.org/en/Content/ArticleLanding/2016/CP/C6CP04883H#!) 
(also on [GitHub](https://github.com/NMRLipids/lipid_ionINTERACTION/blob/master/Manuscript/LIPIDionINTERACT.pdf)).
The effects on the charged lipids (e.g. POPS) are even more severe
as was found in the [NMRlipids project IV](https://github.com/NMRLipids/NMRlipidsIVotherHGs/blob/master/Manuscript/manuscriptPS.pdf) published [here](https://doi.org/10.1021/acs.jpcb.9b06091). 
The agreement with experiments in that study is, again, 
[substantially improved after including the effects of electronic polarization](https://pubs.acs.org/doi/10.1021/acs.jctc.9b00824). 

Further developments and improvement of ECC lipid force fields takes place in 
[ECC-lipids repository](https://jmelcr.github.io/ecc_lipids/). 

The electronic polarization [needs to be included for accurate simulations of biomolecules](https://www.frontiersin.org/articles/10.3389/fmolb.2019.00143/full)). 
The "ECC-models" offer an inexpensive solution, 
which is computatinally even as cheap as any other fixed-charged model,
yet it is polarizable - *implicitly polarizable*. 

