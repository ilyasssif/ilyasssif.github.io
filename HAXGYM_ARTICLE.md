# Accelerating Multi-Agent Reinforcement Learning with JAX: Inside HaxGym

**Author:** Ilyass Sif (@re3gi)  
*Software Developer & Machine Learning Researcher*  
*Website:* [https://re3gi.github.io](https://re3gi.github.io)  
*GitHub:* [https://github.com/re3gi/HaxGym](https://github.com/re3gi/HaxGym)

---

### Introduction

In traditional Reinforcement Learning (RL), simulation environments frequently become the primary computational bottleneck. Standard Python-based physics loops and legacy CPU simulators struggle to produce the millions of transition steps per second required to train complex multi-agent policies.

To tackle this challenge for competitive multi-agent 2D environments, I designed and developed **HaxGym** — a high-performance, fully hardware-accelerated reinforcement learning simulation built from scratch in **JAX**.

---

### The Architecture of HaxGym

HaxGym is modeled around the mechanics of Haxball (a 2D physics-based team soccer simulation). Simulating real-time player momentum, disc collisions, field boundaries, and goal conditions in pure Python or standard C++ bindings often incurs high inter-process communication overhead.

With JAX, HaxGym eliminates IPC bottlenecks by running the entire environment loop directly on the accelerator (GPU / TPU):

1. **Purely Functional Physics Engine**:
   Every state update in HaxGym is implemented as a pure function:
   $$\text{step}(s_t, a_t) \rightarrow s_{t+1}, r_t, d_t, \text{info}$$
   Because there is no mutable internal state, the entire environment state transition is deterministic and effortlessly parallelizable.

2. **Vectorization with `jax.vmap`**:
   Instead of managing multiprocessing pools or asynchronous worker threads, thousands of independent environment instances are stepped simultaneously across hardware cores using `jax.vmap`.

3. **Just-In-Time Compilation with `jax.jit`**:
   The physics integration, collision detection algorithms, and reward calculations are compiled into fused XLA kernels, delivering orders-of-magnitude faster environment steps compared to conventional gym environments.

---

### Key Technical Challenges

- **Continuous 2D Rigid Body Collisions in Pure JAX**: Implementing disc-to-disc and disc-to-segment collision resolution without branching or mutable state requires formulating continuous collision responses via vector operations.
- **Multi-Agent Coordination**: Providing observation spaces suitable for decentralized partially observable Markov decision processes (Dec-POMDP) while maintaining unified tensor shapes for vectorized batches.

---

### Pretrained Models & Hugging Face Release

As part of the project, trained checkpoints and futsal policy weights have been published to the Hugging Face Hub under the **RE3GI** profile (`Haxball-futsal-3x`). These models showcase policy emergence in competitive 3v3 team scenarios, including passing, spatial positioning, and interception dynamics.

---

### Conclusion & Next Steps

Vectorized, compiler-driven simulation is reshaping modern reinforcement learning. By leveraging JAX's transformation primitives, HaxGym demonstrates that competitive, physics-based multi-agent environments can achieve massive throughput on single consumer accelerators.

Explore the source code, benchmarks, and experiment configs at:
* **GitHub Repository:** [re3gi/HaxGym](https://github.com/re3gi/HaxGym)
* **Models on Hugging Face:** [huggingface.co/RE3GI](https://huggingface.co/RE3GI)
* **Author Profile:** Ilyass Sif ([re3gi.github.io](https://re3gi.github.io))
