---
# try also 'default' to start simple
theme: seriph
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: https://cover.sli.dev
# some information about your slides (markdown enabled)
title: CST 363
info: |
  ## ER Diagrams
# apply UnoCSS classes to the current slide
class: text-center
# https://sli.dev/features/drawing
drawings:
  persist: false
# slide transition: https://sli.dev/guide/animations.html#slide-transitions
# enable MDC Syntax: https://sli.dev/features/mdc
mdc: true
# duration of the presentation
duration: 35min
---

# ER Diagrams

CST 363


---

## Lecture Objectives

<div class="p-5">

After this lecture, you should be able to:
- Draw diagrams from ER models
- Define "weak entity set"
- Be able to distinguish weak and strong entity sets


</div>

---

## Motivation

<div class="p-5">


- We want to share the conceptual design with a wide range of stakeholders 
- Most stakeholders won’t know about database schemas or conceptual modeling
- How to share a conceptual model?

</div>


---
layout: center
---


## ER diagram basics


---

## Attributes of entity sets


---

## Primary keys of entity sets

indicate the attributes that form the primary key of an entity set:


---

## Attributes of relationship sets

Put attributes of relationship sets:


---

## Mapping cardinalities

Show that each a student can have at most one advisor:


---

## All kinds of mapping cardinalities



---

## Crow’s Foot — 1:1


---

## Crow’s Foot — 1:M

<img src="/images/crow2.PNG" />

- Each instructor can advise multiple students.
- Each student may have an advisor (optional).



---

## ER diagram for a university



---

## Summary

- ER models can be visualized.
- This helps the data designer, and also helps when sharing a model with stateholders.
- One complication is “weak entity sets”.



