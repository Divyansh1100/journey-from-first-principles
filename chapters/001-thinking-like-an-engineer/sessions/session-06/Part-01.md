# Session 06 — From One Computer to a Scalable System

> **Book:** *Journey From First Principles*
> **Chapter:** Thinking Like an Engineer

---

# Session Information

| Attribute              | Details                      |
| ---------------------- | ---------------------------- |
| Session Number         | 06                           |
| Difficulty             | 🟡 Beginner → Intermediate   |
| Status                 | 🟠 In Progress (Part 1 of 3) |
| Estimated Reading Time | 35–45 Minutes                |
| Prerequisites          | Sessions 01–05               |

---

# Session Objective

Until this point, the discussions focused on understanding how online platforms receive, store and deliver information.

However, one important question remained unanswered.

> **Can one computer alone power a platform that serves millions of users?**

Instead of beginning with technical terminology, this session starts with a simple thought experiment.

The objective is **not** to learn about existing technologies, but to understand **why large systems cannot depend on a single machine** and how engineers naturally begin designing scalable architectures from first principles.

---

# Observation

Imagine building a small video-sharing website.

Initially, only a few friends use it.

The website runs directly on a personal laptop.

```
Your Laptop
     │
     ▼
Website
     │
     ▼
10 Users
```

Everything works perfectly.

The laptop stores uploaded videos.

The processor handles every request.

The storage is sufficient.

The system feels responsive.

No additional infrastructure appears necessary.

---

Now imagine the same platform becomes unexpectedly successful.

Instead of ten users, it now serves:

* Thousands of daily visitors.
* Millions of uploaded videos.
* Millions of simultaneous viewing requests.

The same laptop that previously worked perfectly now begins to struggle.

The website slows down.

Requests begin waiting.

Storage fills rapidly.

Eventually, the system becomes unreliable.

This simple observation raises an important engineering question.

---

# Core Question

> **If one computer is no longer sufficient, what should an engineer do next?**

Should a larger computer simply replace the existing one?

Or is there a fundamentally different way of thinking about the problem?

---

# Initial Hypothesis

The following hypothesis was proposed before introducing any technical concepts.

When a user uploads a video, the website receives the uploaded file.

The system processes the video by storing it in an organized manner together with related information such as its title and other metadata.

Whenever another user requests that video, the website retrieves the stored information and delivers a copy of the content to the requesting user.

This process functions effectively while the number of users remains relatively small.

However, as millions of users begin uploading, searching and watching videos simultaneously, two major limitations naturally emerge.

The first limitation is **storage**.

A single laptop cannot continue storing an ever-growing collection of videos.

The second limitation is **processing capability**.

The processor must now handle thousands or millions of independent activities occurring at the same moment.

These include:

* Uploading new videos.
* Processing uploads.
* Searching for content.
* Retrieving stored information.
* Delivering requested videos.
* Managing many users simultaneously.

From this reasoning, the following conclusion was proposed.

Instead of relying on one computer, it would be more practical to create a **network of computers** that together share the workload.

---

# Reasoning Journey

## Stage 1 — Identifying the First Bottleneck

The discussion began with an apparently simple assumption.

> If more users arrive, simply buy a more powerful computer.

Initially, this appears reasonable.

A faster processor should process requests more quickly.

A larger storage device should hold more videos.

More memory should allow more users to connect simultaneously.

At first glance, increasing the capacity of the existing machine seems like the obvious solution.

However, engineering rarely stops at the first solution.

Instead, engineers immediately ask another question.

> **What new problems does this solution introduce?**

---

## Stage 2 — Looking Beyond Performance

Rather than focusing only on storage and processing power, another possibility was considered.

Suppose an extremely powerful computer is purchased.

It is capable of handling every request.

It stores every uploaded video.

It serves every user.

Now imagine that this single computer unexpectedly fails because of a hardware fault, power failure or any other unforeseen circumstance.

Immediately, every service provided by the platform stops.

No uploads are accepted.

No videos can be watched.

No searches can be performed.

The entire platform becomes unavailable because every responsibility depended upon a single machine.

This observation shifted the discussion away from performance and towards a much deeper engineering concern.

> **Reliability is just as important as speed.**

---

## Stage 3 — First Architectural Proposal

Instead of concentrating every responsibility into one computer, an alternative design was proposed.

Rather than purchasing one extremely powerful machine, a collection of computers should work together as a single system.

```
               Users
                  │
                  ▼
      ┌────────┬────────┬────────┐
      ▼        ▼        ▼
 System A   System B   System C
      │        │        │
      └────────┴────────┘
```

Each computer would participate in serving the platform.

If one system temporarily stopped working, the remaining systems would continue serving users while repairs or replacements could be performed.

This proposal introduced an important shift in thinking.

The objective was no longer to build **a stronger computer**.

The objective became **building a stronger system**.

This distinction marks one of the first major transitions from programming to systems engineering.

---

# Refined Understanding (Current)

At this stage of the discussion, the understanding had already evolved significantly.

Initially, it seemed reasonable that increasing computing power alone would solve the problem of growth.

However, deeper reasoning revealed that performance is only one characteristic of a successful system.

Large engineering systems must also continue functioning when individual components fail.

Therefore, increasing power alone is insufficient.

The architecture itself must be designed to tolerate failure.

This realization naturally leads to a new engineering question.

If many computers are working together, how should responsibilities be divided among them?

That question becomes the starting point for the next stage of the discussion.

---

# Engineering Principle

> **Engineering is not the art of building the strongest component.**

> **It is the art of building the strongest system.**

A system should continue performing its purpose even when individual components experience failure.

This principle will guide every future discussion about large-scale software systems.

---

# Visual Summary

```
Initial Thinking

One Bigger Computer

        │

        ▼

Problem Solved?

        │

        ▼

No.

Single Point of Failure

        │

        ▼

New Thinking

Many Computers

        │

        ▼

Shared Responsibility

        │

        ▼

Greater Reliability
```

---

# Questions That Emerged

By the end of this stage, several important questions remained unanswered.

* If many computers work together, how should responsibilities be divided?
* Should every computer store the same information?
* How can unnecessary duplication be avoided?
* How can the system remain efficient while still being reliable?

These questions form the foundation of the next part of this session.
