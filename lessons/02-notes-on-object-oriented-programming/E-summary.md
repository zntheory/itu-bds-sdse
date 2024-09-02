---
title: "Differences between inheritance in Python and composition in Go"
description: "We look at inheritance vs composition"
keywords:
  - Software engineering
  - Data science
  - Go
  - Lasse Lund Sten Jensen
---

# Differences between inheritance in Python and composition in Go

</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>

**Key Points about Inheritance in Python:**

- Establishes an **"is-a"** relationship. For example, a `Dog` is an `Animal`.
- Encourages reuse of code but can lead to tightly coupled code and complex hierarchies.
- Supports polymorphism, where a subclass can be used wherever its superclass is expected.
- Enables code reuse and establishes a hierarchical relationship between classes.

</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>
</br>

**Key Points about Composition in Go:**

- Encourages a **"has-a"** relationship. For example, a `Dog` has an `Animal` (behavior).
- Promotes loose coupling and flexible code structure.
- Composition is often preferred in Go for its simplicity and the ability to easily mix and match behaviors.
- Go supports embedding, where methods of the embedded type are promoted to the embedding type, allowing behavior similar to inheritance without the tight coupling.

</br>
</br>
