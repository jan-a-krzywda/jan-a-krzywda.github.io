---
layout: post
title: "The Lego Test: How much systems thinking does an LLM have?"
date: 2026-04-08 04:28:31 +0000
image: /assets/images/footnail.png
categories: ["Uncategorized"]
original_url: "https://jan-a-krzywda.com/lego-test-how-much-systems-thinking-llm-has/"
---

This post is a more practical take following the previous [post](https://jan-a-krzywda.com/listened-blocks-of-intelligence-why-ai-needs-systems-engineering-and-the-scientific-method/) on Bayesian thinking and systems engineering for the future of AI.

---

We had a few days off, so we were playing with Legos. At some point, my 6-year-old son suggested, "Can we ask this robot (LLM) to build something with Legos?" I said, "Sure, but you do the building." He started to scatter random Lego pieces on the floor, I took a photo, and Gemini's task was to come up with a design for a new Lego creation using the pieces in the photo.

I didn't expect much success. After all, I was asking an autoregressive model to do something that goes beyond mere pattern recognition. It requires an understanding of the physical properties of the pieces, the models of individual components (including their three-dimensional shapes), and, most importantly, the way they interact with each other. In particular, I was expecting the model to come up with some kind of "Lego soup," a tower, or some rather universal (high-entropy) design, rather than something specific and functional.

To my surprise, in two out of two trials, my favorite LLM came up with very specific designs for an island cottage and a hover/catamaran (?).

<div class="fig-row">
<div class="fig-col" style="flex-basis:33.33%">
<figure class="post-figure">
  <img src="{{ site.baseurl }}/assets/images/Gemini_Generated_Image_286ogb286ogb286o-1-672x1024.png" alt="" loading="lazy" />
</figure>
</div>

<div class="fig-col" style="flex-basis:66.66%">
<figure class="post-figure">
  <img src="{{ site.baseurl }}/assets/images/Gemini_Generated_Image_wn14vpwn14vpwn14-1-1024x768.png" alt="" loading="lazy" />
</figure>
</div>
</div>

Naturally, my next question was, "Ok, son, can you now follow the instructions and build the piece?" Note that this verification and validation phase was carried out by a 6-year-old, so it wasn't incredibly rigorous, but it was enough to confirm that the design was indeed specific and functional. Several failures were reported, including:

- Wrong identification of pieces (most common)
- Wrong dimensions of existing pieces (also common)
- Incompatible shapes (rarely, but still)
- Inconsistent instruction (see above)
- Impossible design (very rarely)

The results are presented in the table below, where each row corresponds to the scattered blocks, the expected outcome, and the outcome of the building process.

<figure class="post-figure">
  <img src="{{ site.baseurl }}/assets/images/post_legod-1024x583.png" alt="" loading="lazy" />
</figure>

Overall, the results certainly do not allow us to reject the hypothesis that current LLM-diffusion model combinations already possess some basic systems thinking capabilities. In fact, most of the errors can be attributed to the incorrect identification of pieces, a problem with the input data (a single 2D image) rather than the model itself. However, one clear limitation remains in the verification phase, where the testing of the design has to be carried out by a human, which is not ideal. In the future, it would be interesting to see if we can automate that process as well, for instance, by using a robotic arm to build the design and test its functionality, or alternatively, by using a physics engine to simulate the design and evaluate its performance. Overall, more rigorous research—beyond two random trials and an underage post-doc, might be required.
