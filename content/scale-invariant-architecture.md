+++
title = "Scale-Invariant Architecture"
date = 2023-04-30
[taxonomies]
authors = ["Ramnath R Iyer"]
tags = ["design"]
+++

Modern distributed system architectures typically incorporate two tiers. The first tier is a stateless application fleet of virtual instances that fronts incoming traffic and executes application code. The second tier is a database that scales independently of the application fleet (for instance, it may be *horizontally sharded* for elasticity). This idea of separating the application from its persistent state and scaling them independently has sustained through the evolution of distributed systems over the years. While any such architecture has its own unique challenges, this pattern has worked relatively well in terms of cost, maintenance, and operations.

Machine learning (ML) models are currently disrupting conventional software. In particular, since ML models are trained on data to reflect the statistics of otherwise undefined algorithms, the separation of the application from its persistent state is no longer viable. The model *is*, in fact, the application as well as the database. Consequently, figuring out how to scale and operate Large Language Models (LLMs) in a cost-efficient manner is an unsolved problem that is being actively researched. Our first step in this direction to hypothesize a *scale-invariant architecture* for ML models. "Scale-invariance" means that the architecture is *fractal* (self-similar) in nature: within some lower and upper bounds, the architecture looks the same no matter how much you zoom in or zoom out (see the figure below for an illustrative example of a fractal). The [actor model](https://en.wikipedia.org/wiki/Actor_model) can serve as excellent starting point for designing such an architecture.

![Sierpinski Triangle Evolution](/sierpinski_fractal.svg)
*Sierpinski Triangle Evolution*

In my next post, I will follow up with a summary of related papers Hewitt, C. (2010)[^1] and Agha, G. (1986)[^2], along with implications on how the actor model should be adapted for operating ML models.

# References

[^1]: Hewitt, C. (2010). Actor model of computation: scalable robust information systems. arXiv preprint arXiv:1008.1459.

[^2]: Agha, G. (1986). Actors: a model of concurrent computation in distributed systems. MIT press.
