---
layout: post
title:  "Molecular antennae made easily visible by Linear Dichroism Imaging"
author: jmelcr
permalink: blog/LDImaging
---

What year did I start my PhD? 
2013?
Luckily, we have chosen the topic of my PhD research 
at that time to be broad enough 
to accommodate almost anything biomembrane related.
The title was:
_"Simulation of processes in cellular membranes"_

What I did and what later formed my doctoral thesis you probably already know. 
I have written a [short summary about it](https://jmelcr.github.io/blog/doc-thesis) some time ago. 
You will not find a word about optical imaging or proteins there. 
Nevertheless, describing the orientation of fluorescent proteins
as molecular antennae should have been the main topic of my research. 

Today, 
I am glad to announce that after about 7 years
this part of research is now (finally!) published
under the title
[Quantitative linear dichroism imaging of molecular processes in living cells 
made simple by open software tools](https://www.nature.com/articles/s42003-021-01694-1)! 
🥳

Doesn't sound like a paper with MD at all, does it? 
Yes, it present mostly the developed tools that 
allows easy and user friendly analysis of the images from polarization microscopy. 
I have helped with the development of the statistical part of the ImageJ plugin,
but where is the MD work?

If you want to jump directly to where the simulations plug into the research,
you need to scroll all the way to 
[Figure 6](https://www.nature.com/articles/s42003-021-01694-1#Fig6),
where we compare our results from MD and this microscopy technique. 
This is important for the imaging analysis tool,
because it justifies some choices made in its statistics. 
(be aware that many experiments contain such "assumptions" often without much checking)

It was impossible to make a converged quantitative distributions with atomistic models. 
We have used various tools, approaches and advanced sampling techniques to try to achieve that, 
but to no avail. 
The results did not agree with what we saw under the microscope. 
Then we gave a try to the Martini 2.2p model
to get a rough estimate of how much more time is needed for convergence. 
Lots of. 
I had to simulate the proteins for about 100 μs "Martini time" 
to get reasonably converged distributions. 
And then we took a look at the results of the optical properties 
from the Martini simulations – and they agreed sufficiently well!

Simpler won over detailed this time. 

And Paretto's "80:20" rule worked again.
(only about 20% of work generates 80% of the results and vice versa)


*That's all nice, Josef, but where's the cake?*
Well, I think that some "inner disinfectant"
is more appropriate nowadays! 😉
Anyways, I am afraid that even 
a glass of a nice peated whisky 
has to wait for some other time
when the corona situation is under a better control. 

At the moment,
you are permitted to have a toast 
when you feel like it this week –
choose your favourite *grain*-based spirit
and say *coarsely* :

_Simulation to infinity and beyond!_
😁

That's how it goes!


PS: 
Would you like to see a very sad real-time experiment
of "what would happen if we did not care about restrictions",
take a look at [the Czech Republic national statistics](https://onemocneni-aktualne.mzcr.cz/covid-19) (deaths are the last grey graph)
(or in English at the European [ECDC](https://www.ecdc.europa.eu/en/covid-19/situation-updates/weekly-maps-coordinated-restriction-free-movement)). 


