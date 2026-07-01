# Session 06 — From One Computer to a Scalable System

## Part 03 — Designing an Adaptive System

---

# Reasoning Journey (Final)

## Stage 7 — Learning from the Real World

After recognizing that copying information everywhere would waste resources, the discussion returned to a familiar real-world system: public libraries.

A personal observation was introduced.

When visiting a local library, it became apparent that not every book published in the world was available.

Upon asking the librarians why this was the case, the explanation was straightforward.

Different communities have different interests.

Instead of storing every possible book, libraries study the needs of their readers and acquire books that are most likely to be useful for that community.

Less frequently requested books are obtained only when necessary.

This observation significantly changed the direction of the discussion.

Rather than attempting to distribute every piece of information everywhere, it became reasonable to distribute information according to demand.

---

## Stage 8 — Introducing Demand Awareness

A new architectural idea gradually emerged.

Instead of continuously producing copies of every piece of content, each level of the system should maintain only an appropriate working stock.

The proposed hierarchy evolved into the following model.

```text
World Library
        │
        ▼
National Libraries
        │
        ▼
Local Libraries
        │
        ▼
Readers
```

Each level possesses a different responsibility.

The World Library maintains the original collection.

National Libraries coordinate distribution across an entire country.

Local Libraries directly serve readers while maintaining only the amount of stock appropriate for their community.

When demand increases, additional copies are produced.

When demand remains low, unnecessary duplication is avoided.

This architecture attempts to balance accessibility with efficient use of resources.

---

## Stage 9 — Prediction Is Guidance, Not Authority

The discussion then explored another situation.

Suppose a prediction department estimates that a particular city will soon experience increased demand for a certain book.

Should thousands of copies immediately be printed?

The answer gradually became clear.

No.

Prediction should not directly control the behaviour of the system.

Instead, prediction serves as an early warning mechanism.

It prepares the system.

It encourages readiness.

It allows resources to be positioned intelligently.

However, the actual production of additional copies should still depend upon genuine demand.

This distinction became one of the most important conclusions of the session.

Prediction improves preparedness.

Reality determines action.

---

## Stage 10 — Distribution of Responsibility

The discussion then reached an even deeper level.

Instead of allowing one central authority to manage every operation, responsibilities themselves should be distributed.

Each level of the hierarchy performs only the tasks appropriate to its role.

```text
World Library

↓

Maintains global collection
Coordinates worldwide distribution

────────────────────────

National Libraries

↓

Coordinate distribution inside the country

────────────────────────

Local Libraries

↓

Maintain local stock
Serve readers directly

────────────────────────

Readers

↓

Consume information
```

This approach reduces unnecessary centralization.

Each participant understands its own responsibility.

Each level becomes accountable for its own decisions.

Rather than one enormous system attempting to solve every problem, the workload is naturally divided.

---

## Stage 11 — Cooperation Beyond Hierarchy

The final discussion considered another situation.

Suppose one city suddenly experiences an unexpected increase in demand.

Nearby cities already possess additional copies.

Instead of waiting for the highest level of the hierarchy to solve the problem, neighbouring libraries can cooperate directly.

```text
        City A
      ↗   ↑   ↖
City B ← City C → City D
      ↘   ↓   ↙
        City E
```

Information and resources can therefore move horizontally as well as vertically.

This realization completed the architectural model developed throughout the session.

A scalable system is not simply a hierarchy.

It is a cooperative network whose participants assist one another whenever circumstances require.

---

# Refined Understanding

At the beginning of this session, the problem appeared to concern only computing power.

It gradually became evident that building large systems is not simply about purchasing stronger hardware.

A scalable system must satisfy several objectives simultaneously.

It should continue operating when components fail.

It should avoid wasting computational resources.

It should distribute responsibilities appropriately.

It should remain flexible enough to respond to changing circumstances.

It should use prediction intelligently without becoming dependent upon prediction.

Finally, different parts of the system should cooperate whenever cooperation produces a better outcome than rigid central control.

The objective is therefore not to eliminate every possible problem.

The objective is to create a system capable of adapting to continuously changing conditions.

---

# Final Mental Model

By the conclusion of this session, the following mental model had emerged.

```text
Small Systems

↓

One Computer

↓

Growth

↓

Need More Capacity

↓

Many Computers

↓

Need Reliability

↓

Need Efficient Distribution

↓

Need Intelligent Resource Allocation

↓

Need Demand Awareness

↓

Need Distributed Responsibility

↓

Need Cooperation

↓

Adaptive Scalable System
```

This model represents the complete evolution of thought developed throughout the discussion.

---

# Engineering Principles

## Principle 01

**Strong systems are built from cooperation, not from a single powerful component.**

---

## Principle 02

**Every engineering solution introduces new trade-offs.**

Solving one problem frequently creates another.

Engineering therefore consists of managing compromises rather than eliminating every limitation.

---

## Principle 03

**Prediction should guide decisions, not replace reality.**

Forecasts improve preparedness.

Real-world demand determines action.

---

## Principle 04

**Responsibilities should be distributed according to capability.**

Well-designed systems assign each participant a clearly defined responsibility.

No component should attempt to perform every task.

---

## Principle 05

**Adaptability is one of the defining characteristics of scalable systems.**

Large systems survive not because they never experience failure, but because they continue functioning despite continual change.

---

# Evolution of Thought

```text
One Computer

↓

Need More Power

↓

Need Reliability

↓

Need Multiple Systems

↓

Need Backup

↓

Need Efficient Distribution

↓

Need Resource Optimisation

↓

Need Demand Awareness

↓

Need Distributed Responsibility

↓

Need Cooperation

↓

Adaptive System Thinking
```

---

# Key Takeaways

* Increasing hardware alone cannot solve large-scale engineering problems.
* Reliability and efficiency must be considered together.
* Information should be distributed intelligently rather than blindly duplicated.
* Prediction is valuable when used as preparation rather than unquestioned instruction.
* Responsibilities should be divided across multiple participants.
* Cooperation between independent components improves resilience.
* Good engineering balances competing objectives instead of searching for perfect solutions.

---

# Open Questions

Although this session answered why a single computer is insufficient, many practical questions remain.

* Where do thousands of cooperating computers physically exist?
* How do these computers communicate with one another?
* How is work divided between them?
* How does a user unknowingly interact with thousands of computers while believing they are communicating with only one website?

These questions naturally become the starting point of the next session.

---

# Session Reflection

This session marked an important transition in the journey.

Previous sessions focused primarily on understanding how information moves through digital systems.

This discussion shifted the focus towards architecture.

Instead of asking how individual components function, the discussion explored how many independent components cooperate to build systems capable of serving millions of users.

The conclusion of the session is therefore not a specific technology or algorithm.

It is a change in perspective.

Engineering is not merely the construction of individual machines.

Engineering is the thoughtful organisation of many independent parts into a system that continues to function, adapt and evolve as the world around it changes.
