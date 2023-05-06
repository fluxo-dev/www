+++
title = "Actor Model"
date = 2023-05-06
[taxonomies]
authors = ["Ramnath R Iyer"]
tags = ["design"]
+++

The actor model is a mathematical theory that treats *actors* as the universal primitives and basic building blocks of concurrent computation. In this post, I highlight key ideas associated with the [actor model](https://en.wikipedia.org/wiki/Actor_model) extracted from Hewitt, C. (2010)[^1]. The title of this paper is *Actor model of computation: scalable robust information systems*.

In the actor model, message passing using types is the foundation of system communication, where (1) messages are the unit of communication, and (2) types enable secure computation with any actor.

Messages are decoupled from the sender and delivered by the system on a best-effort basis. Once a message has been sent, it is the responsibility of the receiver. When an actor receives a message, it can *concurrently* (1) send messages to (unforgeable) addresses of actors it has, (2) create new actors, and (3) designate how to handle the next message it receives.

In processing a message, an actor can send messages only to addresses for which it has information by the following means: (1) that it receives in the message, (2) that it already had before it received the message, or (3) that it creates while processing the message.

Computation is implemented in adherence with information system principles that provide *inconsistency robustness*. **There is no central arbiter of truth.** These principles are: (1) **persistence**; information is collected and indexed, (2) **concurrency**; work proceeds interactively and concurrently, overlapping in time, (3) **quasi-commutativity**; information can be used regardless of whether it initiates new work or becomes relevant to ongoing work, (4) **sponsorship**; sponsors provide resources for computation, (5) **pluralism**; information is heterogenous, overlapping, and often inconsistent, and (6) **provenance**; the provenance of information is carefully tracked and recorded.

In my next post, I will reference a basic implementation of the actor model that will form the basis of a *scalable distributed neural network*.

# References

[^1]: Hewitt, C. (2010). Actor model of computation: scalable robust information systems. arXiv preprint arXiv:1008.1459.