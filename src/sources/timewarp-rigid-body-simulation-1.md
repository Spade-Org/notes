
# Metadata

---

DOI: /

Date: /

---

Tags: #distributed #physics

# Timewarp Rigid Body Simulation

#### Summary
This paper introduces a Timewarp Rigid Body Simulation method to improve the scalability of physics simulations involving hundreds of interacting bodies. Traditional simulation algorithms suffer from poor scaling due to unnecessary synchronization, which causes all bodies to stop or roll back for a local event like a collision. The method adapts Jefferson's optimistic timewarp algorithm from discrete event simulation, allowing individual bodies (or contact groups) to advance asynchronously. When an event is missed or arrives late, only the affected bodies are rolled back. This reduces wasted computation and is shown to offer significant performance improvements for large-scale systems, while also laying the foundation for parallel implementations.

#### Key Insights
Scalability Bottleneck is Synchronization: The main limit to large-scale simulation is not the physics models but the forced synchronization in traditional high-level loops.

Optimistic Asynchrony Works: Applying the timewarp algorithm allows bodies to proceed optimistically and asynchronously. Rollback becomes a more efficient mechanism than global synchronization for managing event causality and reducing wasted work.

Dynamics as Discrete Events: Rigid body simulation, while continuous, can be effectively treated as a discrete event system where discontinuities (collisions, contacts) trigger asynchronous updates.

Dynamic Group Management is Key: The paper shows how to extend timewarp to handle fluid contact groups (collections of touching bodies) by treating each group as a single, dynamic process that can fuse or fission, solving a major challenge for realism.

### Source:
- [https://graphics.stanford.edu/courses/cs448-01-spring/papers/mirtich.pdf](https://graphics.stanford.edu/courses/cs448-01-spring/papers/mirtich.pdf)
