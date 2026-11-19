# Why the Why Matters
What, Why, How: Building a Common Understanding
## Basic
::: mermaid
flowchart TD
    what["What"]
    why["Why"]
    common(("Common Ground"))
    how["How"]
    what --> common
    why --> common
    common ~~~ how
    how --> common
  style common fill:#ffe0b2,stroke:#fb8c00
:::
## Requirements
::: mermaid
flowchart TD
    subgraph Requirement
        what["What"]
        why["Why"]
    end
    common(("Common Ground"))
    how["How"]
    what --> common
    why --> common
    common ~~~ how
    how --> common
  style common fill:#ffe0b2,stroke:#fb8c00
:::
## Actors
:::mermaid
usecase-beta
    direction LR
    actor requester
    actor implementer
    common("Common Ground")
    requester --- common
    common --- implementer
:::
# Scenarios
Actors:
- Requester [R]
- Implementer [I]
## 1. A simple cup of coffee
### Requirement
- What: [R] I want a cup of coffee.
- Why: [R] Because I'm cold.
### How
[I] I will take the first coffee I can find and give it to [R].
### Result
- Got: a warm cup of coffee.
- Expected: a coffee that also tastes good.
- Gap: [R] never said the coffee should taste good, so [I] could not know.
### Lesson
An expectation that is not in the requirement is only met by luck.
## 2. A detailed cup of coffee
### Requirement
- What: [R] I want a good cup of coffee made from Colombian beans.
- Why: [R] Because I'm cold.
### How
[I] We don't have Colombian beans. The why says [R] is cold, and any warm coffee solves that, so I will take the first coffee I can find and give it to [R].
### Result
- Got: a warm cup of coffee.
- Expected: a good coffee made from Colombian beans.
- Gap: the why did not explain the beans, so [I] treated them as optional and dropped them.
### Lesson
A detailed what is not enough. Every detail without a why looks optional to the implementer.
## 3. A detailed cup of coffee with a complete why
### Requirement
- What: [R] I want a good cup of coffee made from Colombian beans.
- Why: [R] Because I'm cold, and Colombian beans are gentle on my sensitive stomach.
### How
[I] We don't have Colombian beans. The first coffee I can find would warm [R] but would not be gentle on the stomach. We have Brazilian beans that are gentler than the basic ones, so I will use those and tell [R] about the change.
### Result
- Got: a warm cup of coffee made from Brazilian beans.
- Expected: a good coffee made from Colombian beans.
- Gap: none that matters. The beans differ, but both reasons are met, so [R] accepts it.
### Lesson
When every part of the what has a why, the implementer can change the what and still meet the need.
## 4. A detailed cup of coffee with a question
### Requirement
- What: [R] I want a good cup of coffee made from Colombian beans.
- Why: [R] Because I'm cold.
### Clarification
- [I] We don't have Colombian beans. Why those beans in particular?
- [R] They are gentle on my sensitive stomach.
- [I] We have Brazilian beans that are gentler than the basic ones. Would that work?
- [R] Yes, that works.
### How
[I] I will make a cup of coffee from the Brazilian beans and give it to [R].
### Result
- Got: a warm cup of coffee made from Brazilian beans.
- Expected: a warm cup of coffee made from Brazilian beans, as agreed.
- Gap: none. [R] and [I] agreed on the change before the coffee was made.
### Lesson
When the why is incomplete, asking is cheaper than guessing. One question turned the same requirement that failed in scenario 2 into a common understanding.