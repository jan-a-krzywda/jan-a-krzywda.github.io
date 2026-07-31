---
layout: post
title: "The Valley of Death: Why Quantum Systems Engineering Never Really Took Off"
date: 2026-02-15 07:34:01 +0000
categories: ["Uncategorized"]
original_url: "https://jan-a-krzywda.com/the-valley-of-death-why-quantum-systems-engineering-never-really-took-off/"
image: /assets/images/image-32.png
---

In the previous parts, we established that Scientists and Engineers speak different languages, yet they often need to share tools or negotiate common ground. For large projects, this process is most efficient with a **Systems Engineer**, who can define a concrete interface between the two—setting concrete goals for the engineer while framing the open problems for the scientist. We also argued that Quantum Computing clearly requires such a bridge. So, logically, Quantum Systems Engineering (QSE) should be a thriving, booming discipline by now, right?

## Wrong.

Despite a promising start around 2016, when researchers first defined a "structured approach" to the field [1], the true *Systems* community never really took off. While the paper called for adopting the SE lifecycle and V-model, it already hinted at the biggest problem: with entanglement, chunking the system into subsystems is not always possible, and neither is drawing the system boundary. A few years later, a doctoral thesis on the topic [2] attempted to use SE tools, like failure mode analysis, but highlighted another blocker: the lack of suitable engineering models. More recently, the community seems to have concentrated heavily on software and algorithmic aspects [3,4]. In those reviews, we find a plethora of fragmented routines, classical algorithms, and architecture designs [4], but the large picture and architectural standards are still missing.

### 1. Problems of QSE:

1. **Culture Clash:** Physical labs are focused on scientific discovery rather than product reliability.
2. **Model Gap:** We lack "hierarchical models" that can capture the relevant dynamics of the system without getting lost in exponential math.
3. **Skill Gap:** Engineers cannot design these systems without effectively needing a PhD in quantum physics.
4. **Boundaries:** Standard input-output modeling and modularity are difficult due to entanglement, which blurs the "system of interest" boundaries.
5. **Velocity:** The technology is moving so fast that requirements change faster than we can build the system.
6. **Vague Needs:** "Stakeholder Needs" are often ill-defined or rely on quantum hype. Because the "value proposition" of quantum computing is still evolving, requirements are vague and shifting, making it hard to design a system to meet them.
7. **Verification:** Standard engineering relies on testing against a known "truth," but as quantum systems scale beyond classical simulation, we lose the ability to easily verify if the system is actually working as specified.

![]({{ site.baseurl }}/assets/images/image-32.png)

Adapted from [4]. The closest match to full quantum architecture.

### 2. The TRL Gaps (or: "It works in the fridge")

The fundamental problem is the Technology Readiness Level (TRL) gap. The TRL framework defines the stages of technology development from basic research (TRL 1) to fully operational systems (TRL 9). It also identifies many gaps along the way, including technological and commercialization valleys of death. The first one is the "Lab-to-Prototype" gap, where a scientific discovery needs to be turned into a working prototype. The second one is the "Prototype-to-Product" gap, where a prototype needs to be engineered into a reliable, scalable product.

![]({{ site.baseurl }}/assets/images/image-34-1024x566.png)

Technology Readiness Level (TRL) and the different gaps that spin- and superconducting- qubits are currently facing. Adapted from [5]

- Scientists (TRL 1-3)**:** Work in the lab. They are happy if the qubit works *once* to get the plot for the paper.
- Engineers (TRL 6-9)**:** Work in the factory. They need the qubit to work *every time* inside a product.

Quantum Systems Engineering was supposed to fill the void in the middle (TRL 4-6). It was meant to be the discipline that takes a delicate experiment and "wraps" it in reliability, rigorous testing, and scalable architecture. In reality, the gap looks different for different architectures.

For **superconducting qubits**, I believe we are already bridging the second gap (Prototype-to-Product), where university funding should gradually shift towards industry, and the focus should be on building a product rather than publishing papers. While this technology is the most mature, it is not the only one.

A few years behind are **spin qubits**, which are preparing to leapfrog the first gap (Lab-to-Prototype). While still in the university-funded phase, we now face the challenge of building a system that in principle can be scaled up. This requires to move from "hero-device" mentality and to start thinking about reliability, modularity, and manufacturability. This demands a systems engineering mindset and model-based design, but still requires enough academic flexibility to iterate and discover new phenomena. Only once the proof-of-concept is achieved, we can think further about stakeholder needs and a clear value proposition.

### 3. The Plan to Bridge the Gap

To bridge the first gap, we need to:

1. **Formulate a concrete challenge:** achieving this would be equivalent to crossing the first gap. Motivated by the physics of semiconductor qubits, I propose concentrating on the stability of two-qubit gates. This is the most critical part of the system and the one most affected by the "world" around it. (More on this in the next post).
2. **Re-think Modeling:** We must understand the problem of model-based thinking and develop a new approach to modeling quantum systems that is suitable for engineering. I believe this can be achieved by the concept of representation learning, or "world models," which I will discuss in the subsequent post.

Together, these two steps would set the foundation for the growth of quantum systems engineering, in particular for semiconductor qubits. If properly engineered, they can use this gained momentum to catch up to other technologies and be the first to cross the second gap.

[1] Everitt, Mark J., J. De C. Michael, and Vincent M. Dwyer. "Quantum Systems Engineering: A structured approach to accelerating the development of a quantum technology industry." *2016 18th International Conference on Transparent Optical Networks (ICTON)*. IEEE, 2016.
[2] Bjergstrom, Kieran. *Quantum systems engineering*. Diss. Loughborough University, 2020.
[3] De Stefano, Manuel, et al. "The quantum frontier of software engineering: A systematic mapping study." *Information and Software Technology* 175 (2024): 107525.
[4] Khan, Arif Ali, et al. "Software architecture for quantum computing systems—A systematic review." *Journal of Systems and Software* 201 (2023): 111682.
[5] Modern overview of QSE <https://www.theiet.org/impact-society/policy-and-public-affairs/digital-futures-policy/reports-and-papers/quantum-technologies-a-new-frontier-for-systems-engineering>
[6] Scotti, L., Basoalto, H., Moffat, J. et al. Review of Material Modeling and Digitalization in Industry: Barriers and Perspectives. Integr Mater Manuf Innov 12, 397–420 (2023).
[7] More on TR from NASA: <https://esto.nasa.gov/trl/>
[8] Thumbnail from: <https://publicenterprise.org/the-project-finance-valley-of-death/>
