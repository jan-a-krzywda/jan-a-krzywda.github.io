---
layout: post
title: "[Listened] Blocks of Intelligence: Why AI Needs Systems Engineering and the Scientific Method"
date: 2026-03-30 05:29:21 +0000
image: /assets/images/beck.png
categories: ["opinion"]
original_url: "https://jan-a-krzywda.com/listened-blocks-of-intelligence-why-ai-needs-systems-engineering-and-the-scientific-method/"
---

I’ve been away for a bit recently, mostly focusing on toughening up my immune system. Taking some time off, I listened to a couple of episodes of *Machine Learning Street Talk*, and I was thrilled to discover their interviews with Dr. Jeff Beck. His ideas fundamentally altered my perspective on the future of AI in a way that perfectly aligns with systems thinking.

Clearly, I already knew we were living in the golden era of function approximation, my favorite LLM told me that much! But I had never really thought about its true limitations. It seems our current billion-dollar models are spectacular at finding correlations in data... and well, that is essentially all they do. They predict, they pattern-match, and they combine. But they don’t *invent*.

<figure class="post-figure post-embed">
  <iframe src="https://www.youtube.com/embed/9suqiofCiwM" title="This first interview breaks down why current models hit a wall, and introduces the 'Lego block' approach to AI." frameborder="0" loading="lazy" allowfullscreen></iframe>
  <figcaption>This first interview breaks down why current models hit a wall, and introduces the 'Lego block' approach to AI.</figcaption>
</figure>

So, what is missing? If you listen to Dr. Beck, you will hear that we have to stop treating AI as a massive sequence predictor and start treating it as a Bayesian scientist or a systems engineer. Here are my core takeaways.

### 1. The Foundation: A Bayesian Approach to Life

To build a system that thinks, we first have to define what "thinking" actually is. According to Beck, the brain doesn’t just blindly map inputs to outputs; it operates on explicit hypothesis testing.

> *"Bayesian inference provides us with like a normative approach to empirical inquiry and encapsulates the scientific method at large, right. I just believe it's the right way to think about the empirical world."*

A true AI must hold a generative model of the world. When it encounters new data, it asks: *How is this like the old data? Does my current hypothesis hold up, or do I need to update my beliefs?* If you think about it, this is exactly how we do science. We come up with a potentially surprising prediction, distill it into a concrete hypothesis, and then test it against the world. Depending on the outcome, we either update our beliefs or validate existing ones, and move on to the next question. The Bayesian approach is the architectural foundation of our brains and the scientific method. If we want to build a thinking machine, we have to mimic that process.

### 2. The Illusion of Retooling vs. True Systems Engineering

Because current models lack this structured way of probing the world, they are limited to utilizing experiments that have already been done. While they can generate a new hypothesis, they cannot physically construct a new experiment to test it. They have no wind tunnel, no cooking pan, and no toy to throw. One exception might be constructing numerical simulations, like writing Python code, to test hypotheses virtually. Albeit limited by compute power and "vibe-coding" entropy, I believe some creative possibilities already exist there, even with current architectures.

But with limited simulation capabilities, we are left with a bunch of hypotheses that can only match observations already present in the training data. While this is useful for creating connections between isolated knowledge domains, it is not enough to generate genuinely new knowledge.

This stands in stark contrast to how human creativity works, and more importantly, how big breakthroughs in science and engineering happen. We don’t just retool old experiments. Sure, we start by understanding the individual components and forming hypotheses about how they interact. However, the central activity is the sequential process of combining them, break-testing them, and refining our initial models until we achieve an emergent behavior that was never observed before. Beck highlights this perfectly:

> *"I know how an air foil works to create lift, I know how a jet engine works to create thrust... and I can take those two bits of information to invent something brand new which is an airplane... without that the only thing you will ever be able to do is just retool solutions for new purposes."*

### 3. The "Lots of Little Models" Approach

So, how do we get an AI to do systems engineering? Most likely not through one massive neural network, transformer, or whatever the next big monolithic architecture is. Instead, Beck argues for a modular approach, where the AI is an orchestrator of many small, specialized models:

> *"It's going to have a modular description of the world and it's going to have the ability to combine those modules in a way that creates a more sophisticated understanding. It's like Legos... I can build all sorts of new and amazing things that were never built before right out of them. That's a capability that we have and that's the essence of creativity."*

Crucially, each of these small models should be sophisticated enough to model the features relevant to its connections. This can be achieved through active learning, where each subsystem is tested and refined. If a situation requires it, the agent should be able to train a new model from current experience, test it against the world, and incorporate it into its existing library. This is how we move from a collection of isolated facts to a true understanding of the world.

<figure class="post-figure post-embed">
  <iframe src="https://www.youtube.com/embed/Ucqfb33GJJ4" title="For a deeper dive into how these specialized agents communicate and how we keep them safely aligned, check out part two." frameborder="0" loading="lazy" allowfullscreen></iframe>
  <figcaption>For a deeper dive into how these specialized agents communicate and how we keep them safely aligned, check out part two.</figcaption>
</figure>

### 4. Active Inference: Poking the Beach Ball and The Cat in the Warehouse

This points to one of the biggest limitations of modern AI: learning is turned *off* when we deploy the model. One could argue that modern chain-of-thought (CoT) ideas are trying to get around this by forcing the model to refine its own internal reasoning. To me, however, this functions more like feature engineering than continuous learning. The model isn't actively updating its inner parameters; it is just refining its input sequence.

Looping the output back to the input *is* an important step. It mimics hypothesis testing, as the agent effectively tests its own output and refines it until it reaches a sort of convergence (like a Banach fixed point). Yet, it remains limited because this only happens once per prompt. The model cannot permanently learn from the experience and incorporate it into its future behavior.

Hence, it remains very distant from a true Bayesian agent, for whom every experience is an opportunity to learn and refine internal models. Beck calls this process **Active Inference**. It’s not just about passively observing the world; it’s about actively engaging with it, testing hypotheses, and updating beliefs in real time.

Imagine an AI trained to manage a warehouse. It knows about forklifts, boxes, and shelves. One day, a stray cat wanders in.

> *"When a cat comes along [and the AI] doesn't know what a cat is, the surprisal signal goes crazy and then it says 'Okay stop.' Right, don't run over the cat, let's figure out what's going on."*

Instead of hallucinating or crashing, an active agent recognizes what it doesn't know. It pings a massive external server, pulls down a few candidate models ("Is it a dog? A raccoon? A cat?"), tests its hypothesis by, for instance, throwing a ball, and permanently incorporates the "cat" model into its local worldview.

And if it can't observe passively, it experiments. Beck notes that if a robot sees a beach ball for the first time, it should do what a human toddler does: run up, poke it, and see how the physics react. *That* is intelligence.

### 5. Safe Alignment

Finally, how do we make sure this active, scientific agent doesn't accidentally destroy us? If you hardcode a sweeping reward function into a reinforcement learning (RL) agent—say, "end world hunger"—it might calculate that the most efficient solution is to eliminate all humans.

According to Beck, the alternative is to give the agent a more modest, perturbative approach that encourages it to explore without prescribing a sweeping end goal:

> *"Here's the safe way to improve the situation. You don't say end world hunger. You perturb that distribution over outcomes a little bit and then you evaluate the consequences... rather than just specifying one by hand because that's the dangerous thing."*

### 6. Maximum Entropy Inverse Reinforcement Learning

All of this shifts the paradigm toward a framework where the agent learns by interacting with its environment. Specifically, Beck notes that Active Inference can be effectively mapped to a Maximum Entropy Inverse RL framework. Instead of us giving the AI a reward function, the AI observes the steady-state distributions of *human* actions and outcomes to deduce our values. It is rewarded for achieving goals while maintaining a high level of entropy (randomness/flexibility) in its action distribution. This encourages safe exploration and prevents the agent from converging on a single, potentially harmful, dogmatic strategy.

To me, this connects beautifully to physical intuitions related to thermodynamics and statistical mechanics. The trade-off between reward (energy) and exploration (entropy) is balanced by a temperature parameter. This parameter can be dynamically adjusted to encourage more exploration when the agent is stuck in a local minimum, and more exploitation when it is on the right track. Remember the heat you feel when you are stuck in a traffic jam? That might be your internal "temperature" rising, encouraging you to increase your entropy and explore alternative routes.

### Conclusion

To sum up, I find Beck's vision of AI as a modular, active inference agent deeply compelling. It moves us away from the current paradigm of massive, monolithic models that excel at pattern recognition but lack true understanding. Instead, it points toward a future where AI systems are more like scientists or engineers—constantly testing hypotheses, learning from experience, and, most importantly, keeping us in the loop to ensure safe alignment and smooth integration into our world.

Next time, we will do a small experiment to assess the systems thinking capabilities of current LLMs. *Disclaimer: This test was suggested by my 6-year-old son and it includes LEGO blocks.*
