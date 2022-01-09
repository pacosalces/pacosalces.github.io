---
layout: post
title: Defocused imaging
description: (Hardware-based regularization)
---


A story on:
<i style="color:Orange;"> Multiple-camera defocus imaging of ultracold atomic gases </i>
([Optics Express Vol. 29, Issue 11, pp. 17029-17041 (2021)](https://doi.org/10.1364/OE.422981){:target="_blank"})


### Background
Imaging cold atomic gases can prove challenging depending on the method, but also on the requirement on signal-to-noise ratio (SNR) or spatial resolution. Microscopes comprising arrays of lenses, mirrors, and apertures are typically customized to perform this task. The ultimate SNR and spatial resolution are set by the largest numerical aperture closest to the atomic sample. Small errors in alignment of this optical systems can lead to aberrations, such as defocus, that act in detriment of the theoretically attainable resolutions. Nevertheless, optical systems are linear in nature and numerical inversion of the effects of a misaligned optic is possible. However, this inversion is not unique because more than one optical system may yield the same image of an object and the problem becomes ill-posed. This has to do with the optical field phase ambiguity, where after winding up by a certain amount, it becomes hard to unwrap its exact evolution through propagation. An intuitive example of this is in a defocused image; when you have a defocused image, you may not know if the lens needs to be pushed or pulled relative to an object in order to bring it to focus. Numerical inversion suffers from this ambiguous phase inversion only at certain spatial scales, and turns to regularization to "safely ignore" such scales at the cost of losing information.

### Experiment
In this paper led by A. R. Perry, we try to implement a sort of hybrid regularization using both software and hardware. To do this, we prepare samples of ultracold clouds of atoms, and image them in and out of resonance not with one, but three different optical systems (not necessarily near focus). Because we characterize the SNR performance across different detunings from resonant absorption, we refer to the technique as "Multiple camera off-resonant defocused" (McORD) imaging. In the experiment a set of three images are taken simultaneously by three different paths at various detunings from resonance. This produces intensities proportional to atomic column densities with contrasting ring-patterns indicating the amount of defocus in the optical system as well as the detuning from resonance (which makes the cloud act like lens in itself). Then, loss of information in one of the contrast transfer functions (CTFs) can be "plugged" by the other two. In principle, this should improve the SNR, but because of the splitting into three imaging paths, a 3dB penalty is paid at each beamsplitter and the SNR is only nominally restored. 

### Key finding
The heart of this paper is to demonstrate how hardware may be used to assist a regularized inversion of aberrated images with a minimal penalty on SNR. 
