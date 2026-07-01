# Session 06 — From One Computer to a Scalable System

## Part 02 — Designing Beyond a Single Machine

---

# Reasoning Journey (Continued)

## Stage 4 — A New Problem Appears

The idea of replacing one computer with a network of computers appeared promising.

The workload could now be distributed.

If one machine failed, others could continue operating.

However, introducing multiple computers immediately raised another question.

> **If every computer is different, what exactly should each computer store?**

To explore this question, a simple thought experiment was considered.

Suppose four independent computers exist.

```text
Computer A → Stores Video 1

Computer B → Stores Video 2

Computer C → Stores Video 3

Computer D → Stores Video 4
```

Initially, this arrangement appears organized.

Every computer owns a separate responsibility.

Storage is distributed.

The workload is divided.

Everything seems efficient.

Then an unexpected event occurs.

Computer B suddenly fails.

```text
Computer A ✅

Computer B ❌

Computer C ✅

Computer D ✅
```

Immediately a new question emerges.

> **Where did Video 2 go?**

If Computer B stored the only copy of that video, then every user requesting it would receive nothing.

The video has effectively disappeared from the platform.

This revealed another important engineering observation.

Simply distributing work is not enough.

The information itself must also survive hardware failures.

---

## Stage 5 — First Backup Architecture

To overcome this limitation, a new architectural idea was proposed.

Instead of allowing individual computers to permanently own the original information, another level of responsibility could be introduced.

The architecture was imagined as follows.

```text
                Upload
                   │
                   ▼
           Local Sharing System
                   │
                   ▼
        Central Storage Repository
                   │
        ┌──────────┼──────────┐
        ▼          ▼          ▼
     Sharing A  Sharing B  Sharing C
```

The proposal suggested that after receiving new content, the local system forwards it to a central repository responsible for preserving the original material.

Whenever users request that content, the repository identifies an appropriate nearby system capable of serving the request.

If one local system becomes unavailable, another system simply takes over.

The path changes.

The information remains available.

This design appeared to improve reliability considerably.

---

## Stage 6 — Discovering an Inefficiency

However, while explaining this architecture, an important realization emerged.

The information was now travelling through several unnecessary stages.

For a single uploaded video, the following sequence occurred.

```text
User

↓

Local System

↓

Central Repository

↓

Local System Again

↓

User
```

This raised an important concern.

> **Is the same information being processed more times than necessary?**

Although the architecture improved fault tolerance, it also introduced additional processing and communication.

The solution had solved one problem while simultaneously creating another.

This was the first explicit encounter with one of the most important ideas in engineering.

> **Every improvement introduces a cost.**

---

# Refined Understanding

At this point in the discussion, the understanding evolved beyond simply increasing reliability.

Initially, the objective was preventing the platform from failing when one computer stopped working.

Introducing multiple systems successfully addressed this concern.

However, reliability alone could not be considered a complete solution.

Every additional movement of information requires:

* More processing.
* More communication.
* More coordination.
* More time.
* More computational resources.

Consequently, an architecture should not only be reliable.

It must also remain efficient.

This realization transformed the engineering objective once again.

The problem was no longer:

> **How do we avoid failure?**

The problem became:

> **How do we avoid failure without wasting unnecessary resources?**

This subtle change represents an important step in engineering maturity.

---

# A Different Way of Thinking

To better understand the situation, the discussion deliberately moved away from computers.

Instead, a familiar real-world analogy was introduced.

Imagine the world's largest library.

One author writes a new book.

Millions of readers across the world wish to read it.

How should knowledge be distributed?

One obvious possibility would be to keep only one copy.

Although simple, every reader would need to travel to that single location.

The library would quickly become overwhelmed.

A second possibility would be to print copies for every library on Earth.

Readers could now access the book much more easily.

However, enormous amounts of paper, storage and effort would now be required.

Neither solution appears completely satisfactory.

The discussion therefore shifted away from searching for a perfect solution.

Instead, the focus became identifying the most reasonable compromise.

---

# Engineering Principle

> **Every engineering decision is a balance between competing objectives.**

Improving one characteristic often increases the cost of another.

Good engineering is therefore not the search for perfection.

It is the search for the most appropriate trade-off.

---

# Visual Model

```text
One Copy Only

✔ Minimal Storage

✘ Slow Access

✘ Heavy Congestion



Copies Everywhere

✔ Fast Access

✔ High Availability

✘ Huge Resource Consumption



Engineering Goal

↓

Balance

↓

Accessibility

Reliability

Efficiency

Cost
```

---

# Evolution of Thought

```text
One Computer

↓

Many Computers

↓

Failure Protection

↓

Central Backup

↓

More Data Movement

↓

Resource Waste

↓

Need For Balance
```

---

# Questions That Naturally Emerged

At the end of this stage, the discussion had not yet produced a perfect architecture.

Instead, several deeper questions appeared.

* Should every system keep a copy of every piece of information?
* Is every piece of information equally valuable?
* Can information be copied only when necessary?
* Is there a way to predict future demand before users request it?

These questions become the foundation of the final stage of Session 06.
