# Why the Why Matters
What, Why, How: Building a Common Understanding
## Basic
``` mermaid
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
```
## Requirements
``` mermaid
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
```
## Actors
``` mermaid
usecase-beta
    direction LR
    actor requester
    actor implementer
    common("Common Ground")
    requester --- common
    common --- implementer
```
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
- Gap: none that matters this time. The beans differ, but both reasons are met, so [R] accepts it. But [R] only heard about the change after the coffee was made. If Brazilian beans had not worked for [R], the work would have been wasted.

### Lesson
A complete why lets the implementer change the what and still meet the need. The change still rests on the implementer's own assumption, so it is safer to check first, as in scenario 4.

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

## 5. A cup of coffee with an explained how

### Requirement
- What: [R] I want a good cup of coffee made from Colombian beans.
- Why: [R] Because I'm cold, and Colombian beans are gentle on my sensitive stomach.

### How
- What: [I] I will brew a fresh pot of Colombian coffee. It takes ten minutes.
- Why: [I] There is a pot ready, but it has been standing for hours, and coffee that has been standing is harsher on the stomach. A fresh pot is slower but gentler.

### Clarification
- [I] Is ten minutes OK, or do you want a cup from the old pot right away?
- [R] I can wait. My stomach matters more than the ten minutes.

### Result
- Got: a fresh, warm cup of Colombian coffee after ten minutes.
- Expected: exactly that, as agreed.
- Gap: none. Without the explanation, [R] would have seen a ready pot and a ten-minute wait, and wondered why.

### Lesson
The how needs a what and a why too. When the implementer explains the choice and its trade-off, the requester can accept it or object before the work is done. A common understanding is built from both sides.

