---
layout: post
title: "[Our Paper] Statistical Structure of Charge Disorder in Si/SiGe Quantum Dots"
date: 2025-10-17 10:21:17 +0000
categories: ["Uncategorized"]
original_url: "https://jan-a-krzywda.com/our-paper-statistical-structure-of-charge-disorder-in-si-sige-quantum-dots/"
---

I personally believe spin qubits are one of the most promising platforms for large-scale quantum computing. For sure they are on top, in terms of interesting physical phenomena to analyze. Besides that, we are often promising to leverage highly repeatable industrial technologies to create devices containing millions of qubits, but at the current stage, getting tens of fully functional qubits is a challenge.

![]({{ site.baseurl }}/assets/images/image-6-1024x655.png)

**(Left)** Potential landscape of double quantum dot in Si in 3D. **(Right)** Finite element simulation of double quantum dot potential in presence of charge defects and controlled by metallic plunger (PL, PR) and a barrier gate.

Spin qubits live inside an electrically defined potential well. Naturally, the main challenge is the electrostatic disorder, which causes fluctuations of qubit parameters in time and between the qubits. While even small fluctuations degrade the performance of quantum algorithms, large fluctuations can make qubits useless at all, which takes place if our control knobs are not able to bring the qubit to the operational point. There are two most important control knobs: the plunger gate, which digs a deeper well, and the barrier gate, which controls the hills between the wells.

In our new [work](https://arxiv.org/pdf/2510.13578), we tackled this disorder head-on. To understand its true nature, we built a "virtual factory," simulating thousands of double quantum dot devices, each with a unique random distribution of charged defects. This gave us a massive statistical dataset to analyze.

Using a Principal Component Analysis (PCA), we found the disorder isn't just random noise. Instead there are certain "directions" in parameter space that make several of the parameters fluctuate together. Interestingly most of them can be linked to a certain physical process. We discovered that over 80% of all device-to-device variability is concentrated along just three dominant "disorder modes":

![]({{ site.baseurl }}/assets/images/image-4.png)

A symmetric **"squeeze or stretch"** of the two dots, which is the biggest problem.

![]({{ site.baseurl }}/assets/images/image-2.png)

An asymmetric **"tilt"** in their energy levels.

![]({{ site.baseurl }}/assets/images/image-5.png)

A common **"vertical shift"** of the potential.

This discovery led to a clear, practical conclusion about control. A simplified "plunger-only" control scheme is severely limited; it can only compensate for about 50% of the disorder and is almost powerless against the dominant "squeeze/stretch" mode. However, by including the barrier gate in a "three-gate" scheme, we can correct over 90% of the disorder variance.

Our work provides a predictive model to generate realistic data for training future tuning algorithms, puts PCA method on the map as a relevant tool for tuning quantum dots and provides direct evidence for limited capability of plunger-only control.

arXiv: [https://arxiv.org/abs/2510.13578](https://arxiv.org/pdf/2510.13578)
GitHub repo: <https://github.com/jaq-lab/qdot-disorder-structure>
