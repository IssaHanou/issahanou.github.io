---
layout: page
title: Instant Delay Replanning
description: Collaboration project to instantly recover from delays in a multi-agent system.
img: BanffTrain.jpg
importance: 1
category: work
related_publications: 
---

Together with Devin Thomas and Wheeler Ruml from the University of New Hampshire, we're working on applying any-start-time planning to real-world scenarios through the example of delays in Railway Hub Planning.

This work has been published at ICAPS2024, and can be found [here](https://ojs.aaai.org/index.php/ICAPS/article/view/31483). Devin and I presented our paper at the main conference in Banff, Canada in June 2024 and we also gave a poster presentation. I also presented this work at the TU Delft AI PhD Poster Day on June 25, 2024. 

In the paper, we show that we can instantly recover from delays by looking up precomputed plans in nanoseconds, for any delay in our given horizon. The precomputation scales only quadratically in the number of trains and we show that for 50 trains, we can still compute all plans in only seconds. Our paper uses the example of trains in a railway hub, but the method works for any multi-agent system where you can represent the problem as a Safe Interval Path Planning problem by describing the world in terms of safe and unsafe states and actions. 

In future work, we want to extend this to not only temporal delays but also spatial changes to a given plan. Moreover, we want to do further experiments to show the applicability to railway systems in general. 
