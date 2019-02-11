---
layout: post
title:  "Electronic Continuum correction (ECC): Implicit model of polarizability"
author: jmelcr
permalink: blog/ECC-post
---

Polarizable or non-polarizable. 

Do I need it for my simulation? 
Are the effects of the electronic polarization that improtant? 

*May be.*

But is it worth the extra computational effort, 
the order of magnitude slowdown,
when it seems that researchers usually get away without it?

*Look, it does not have to be that dramatic...
I will show you that is possible to get 
a large amount of the effect of electronic polarization 
very cheaply - at zero additional cost -
using the Electronic continuum correction.*

<HR>

When I use the term *polarizability*, 
it is often automatically assumed to mean *explicit polarizability*. 
No one is to be blamed for that,
using explicit polarizable dipoles with Thole damping or
[Drude particles](https://en.wikipedia.org/wiki/Drude_particle)
is a very common way to account for electronic polarization. 
However, there is also a relatively recently developed theory,
which provides an *implicit* model of polarizability,
which we term Electronic Continuum Correction (ECC)
(references: [MD in electronic continuum (MDEC)](http://scitation.aip.org/content/aip/journal/jcp/130/8/10.1063/1.3060164) 
and a [follow-up paper](http://dx.doi.org/10.1021/ct9005807)).

ECC is an implicit model of electronic polarizability,
in which a system of polarizable particles is represented
with an equivalent system of particles with fixed charges
including the effects of electronic polarization *implicitly* in a mean-field way.
It is sometimes incorrectly percieved as being represented with a *non-polarizable* system, 
but the opposite is true - it only takes the same form as classical non-polarizable force fields. 
The relation between the *original* and the *new* set of charges 
is almost trivial - mere linear scaling with a certain factor smaller than one provides the effect. 
That is also the reason why ECC is often referred as the *charge-scaling* approach.
However, that is only a practical realization of
embedding all atoms into a dielectric continuum 
with a high-frequency dielectric constant of the electrons
(hint: scaling charges with the inverse square root of the dielectric constant provides the same effect).
It is important to note that the value of the 
high frequency dielectric constant  
is around 2 for almost any biologically relevant environment.
This means that even interfaces like biological membranes do not contain discontinuities of the electronic continuum. 
Given that the  high frequency dielectric constant of water is 1.78 (i.e., the square of the refraction index), 
the scaling factor for ions in water is roughly 0.75. 

ECC significantly improves the accuracy of simulations of solvated [ions](https://aip.scitation.org/doi/abs/10.1063/1.5006779) 
(freely available [manuscript](http://jungwirth.uochb.cas.cz/assets/papers/paper294.pdf)), 
and it was recently shown by our group that ECC is crucial also for 
[proteins](https://pubs.acs.org/doi/10.1021/acs.jpcb.7b12097) and 
[phospholipids](https://pubs.acs.org/doi/10.1021/acs.jpcb.7b12510)
(also on [GitHub](https://github.com/jmelcr/NMRlipids_VI-NewIonModel/blob/master/Manuscript/manuscript.pdf)).
The research on the latter was largely driven by the [NMRlipids](http://nmrlipids.blogspot.com/) community,
which has found that all current classical force fields 
overestimate the affinity of cations to PC lipid bilayers 
in the recent [publication](https://pubs.rsc.org/en/Content/ArticleLanding/2016/CP/C6CP04883H#!divAbstract) 
(also on [GitHub](https://github.com/NMRLipids/lipid_ionINTERACTION/blob/master/Manuscript/LIPIDionINTERACT.pdf)).
The effects on the charged lipids are even more severe
as is found in the ongoing [NMRlipids project IV](https://github.com/NMRLipids/NMRlipidsIVotherHGs/blob/master/Manuscript/manuscriptPS.pdf),
where mixed PC:PS bilayers are studied. 
The agreement with experiments in that study is, again, substantially improved
after including the effects of electronic polarization,
as I demonstrate in my [current research](https://github.com/jmelcr/ecc_lipids) 
on the interaction of cations with negatively charged membranes.

Simulations with *explicitly polarizable* models are generally considered to be costly for any practical use in biophysics. 
The ECC-models, however, are computatinally as cheap as any other fixed-charged model,
yet they are polarizable - *implicitly polarizable*. 

