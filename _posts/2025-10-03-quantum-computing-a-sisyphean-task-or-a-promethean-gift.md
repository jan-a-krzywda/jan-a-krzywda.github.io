---
layout: post
title: "Quantum Computing: A Sisyphean Task or a Promethean Gift?"
date: 2025-10-03 05:59:09 +0000
image: /assets/images/Gemini_Generated_Image_f56w7pf56w7pf56w-e1759471243693.png
categories: ["Uncategorized"]
original_url: "https://jan-a-krzywda.com/quantum-computing-a-sisyphean-task-or-a-promethean-gift/"
---

I recently fell down a quantum rabbit hole, emerging between two wildly different worlds. First, I watched a video by former physicist Sabine Hossenfelder explaining why she’s done with the hype around quantum computing. Minutes later, my feed showed me a report on the first-ever use of quantum trading, an announcement that helped trigger a 5% stock price jump for IBM.

So, where on this vast spectrum of hype and hope should we stand?

#### **The Sisyphean Skeptics**

On one side, you have skeptics like Dr. Hossenfelder. They argue that quantum computing is dangerously overhyped to attract funding, consuming astronomical resources while remaining decades away from practical use. She warns of a potential "Quantum Winter"—a moment when investors finally call the bluff, funding dries up, and the entire field is set back by years. While this dynamic lies outside of pure science, it is inextricably linked to it through the decisions of funding agencies and venture capitalists.

<figure class="post-figure post-embed">
  <iframe src="https://www.youtube.com/embed/MukMOZ0J-Ww" title="" frameborder="0" loading="lazy" allowfullscreen></iframe>
</figure>

Encouragingly, some in the field are already implementing guidelines to avoid unnecessary hype (See [Ezratty 2022](https://arxiv.org/abs/2202.01925) for the analysis and guidelines). In the long run, this should help shift the investment model from a "fake it till you make it" approach to a more academic "show it to grow it" standard. At the end of the day, such a sustainable, evidence-based growth is far more beneficial for society, even if resources are allocated more slowly. (I believe the same applies to AI, but that’s a topic for another day).

Unfortunately, there is a scarier level to this argument. What if the overpromising also applies to the *potential* of fault-tolerant quantum computers? How much real economic value can be driven by Shor's algorithm breaking RSA encryption if everyone has already migrated to [post-quantum cryptography](https://csrc.nist.gov/projects/post-quantum-cryptography)? What are the gains from Grover's search algorithm if it requires you to [label the solution in advance](https://quantumcomputing.stackexchange.com/questions/27499/to-program-grover-algorithm-oracle-we-need-to-know-the-answer-already-if-we-kn)? What if complex chemistry simulations, like [protein folding](https://www.youtube.com/watch?v=P_fHJIYENdI), become solvable by classical AI, making quantum computers redundant for that task?

These are the provocative questions Dr. Hossenfelder raises. While her tone can be sharp, her core technical points about the immense engineering challenges are valid and shared by many experts. For me, however, this isn't a sign of futility. It is a clear signal that more investment is needed, particularly on the algorithmic side, to find novel and practical applications. There may be plenty of time, but the clock is ticking.

#### **The Promethean Promise**

On the other side of the spectrum are the investors and corporations themselves. Depending on your perspective, they are either pumping the bubble or genuinely reporting a breakthrough. For this section, let's assume the latter.

<figure class="post-figure post-embed">
  <iframe src="https://www.youtube.com/embed/jr6P2ZB5lmM" title="" frameborder="0" loading="lazy" allowfullscreen></iframe>
</figure>

Recently, HSBC and IBM announced what they called a "Sputnik moment" for finance. Their [paper](https://arxiv.org/pdf/2509.17715v1) claim was an "up to 34 percent improvement" in predicting the likelihood of a bond trade being successfully executed. The announcement was a PR success, boosting IBM's stock. But what did they actually do?

They used a quantum computer as an offline tool to preprocess data that was then fed into classical prediction models. Crucially, the 34% performance gain was *only* seen when using real, noisy quantum hardware. When the team ran a perfect, noiseless classical simulation of the exact same quantum circuit, the advantage vanished. This strongly suggests the "quantum advantage" came not from the quantum algorithm itself, but from the hardware's inherent noise. The authors admit this finding is purely empirical and lacks a theoretical explanation.

Despite the positive market response, this "noise as a feature" claim drew sharp criticism from top academics. Quantum complexity theorist Scott Aaronson [dismissed](https://scottaaronson.blog/?p=9170) the paper as a "qombie"—a zombie claim of quantum advantage that refuses to die. He argued the result was likely a "strange artifact" with "nothing really to do with quantum computational speedup." Still, other researchers are intrigued by the findings and see potential avenues for further exploration.

#### **Summary: A Path Through the Middle**

Given the latest news, where should we land on the spectrum? The wisest position, it seems, is the pragmatic middle.

Constructive criticism of the quantum hype is essential to allocate resources wisely. At the same time, every empirical application—even a flawed one—provides valuable hints about where a true quantum advantage might be found, and subsequently proven or disproven. Both skepticism and experimentation are the fuel we need for systematic research that can lead us toward an open and honest quantum future.

---

**Full Disclosure:** Personally, I hope that quantum computing's first major breakthrough isn't in algorithmic trading, but rather in stochastic optimal control. This idea of using structured noise as a resource in hybrid algorithms aligns closely with my own work. In fact, my research group recently received funding to explore quantum computers for stochastic trajectory generation, and I promise to keep you updated on our developments.

<figure class="post-figure">
  <img src="{{ site.baseurl }}/assets/images/image.png" alt="" loading="lazy" />
</figure>

Relevant projects: #[QuantumLearningMachines](https://jan-a-krzywda.com/quantum-learning-machines/)
