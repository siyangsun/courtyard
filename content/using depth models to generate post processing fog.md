---
title: "Using depth models to generate post-processing fog"
tags: 
- room
---

With neural networks it's now possible to [generate a depth map from any image](https://arxiv.org/pdf/1604.03901.pdf). I noticed that generated depth maps often look like the image on an extremely foggy day (almost like a demo of atmospheric perspective)

![[Depth map deep netcomparison.png]]

It's already possible to use depth maps to generate fog: https://www.toolfarm.com/tutorial/creating-fog-in-ae-with-sapphire-create-z-depth-pass-for-dof-fog/

So having a model automatically generate fog on a video using the AI-generated depth maps should also be possible.