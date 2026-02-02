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

<v-clicks>

- Draw diagrams from ER models
- Define "weak entity set"
- Be able to distinguish weak and strong entity sets

</v-clicks>

</div>

---

## Motivation

<div class="p-5">

<v-clicks>


- We want to share the conceptual design with a wide range of stakeholders 
- Most stakeholders won’t know about database schemas or conceptual modeling
- How to share a conceptual model?


</v-clicks>


</div>


---

## ER diagram basics


<div class="p-5">



```mermaid {scale: 0.8}
erDiagram
  contributor {
    int contrb_id PK
  }
  candidate {
    int cand_id PK
  }

  contributor o{--o{ candidate : contribution
```

<br>

- `contributor` and `candidate` are "entity sets"
- `contribution` is a "relationship set"



</div>


---

## Attributes of entity sets

<div class="p-5">


Put attributes of entity sets:


```mermaid {scale: 0.7}
erDiagram
  contributor {
    int contbr_id
    string name
    string zip
  }

  candidate {
    int cand_id
    string name
  }

  contribution {
  }

  contributor ||--o{ contribution : " "
  candidate  ||--o{ contribution :  " "
```

</div>



---

## Primary keys of entity sets

<div class="p-5">


Indicate the attributes that form the primary key of an entity set:

```mermaid {scale: 0.7}
erDiagram
  contributor {
    int contbr_id PK
    string name
    string zip
  }

  candidate {
    int cand_id PK
    string name
  }

  contribution {
  }

  contributor ||--o{ contribution : " "
  candidate  ||--o{ contribution :  " "
```


</div>


---

## Attributes of relationship sets

<div class="p-5">


Put attributes of relationship sets:


```mermaid {scale: 0.7}
erDiagram
  contributor {
    int contbr_id PK
    string name
    string zip
  }

  candidate {
    int cand_id PK
    string name
  }

  contribution {
    int contb_id PK
    decimal amount
  }

  contributor ||--o{ contribution : " "
  candidate  ||--o{ contribution :  " "
```

</div>


---

## Mapping cardinalities


<div class="p-5">


Show that each a student can have at most one advisor:


```mermaid {scale: 0.6}
erDiagram
  student {
    int id PK
    string name
    int tot_cred
  }

  instructor {
    int id PK
    string name
    decimal salary
  }

  instructor o|--o{ student : advisor
```


</div>


---



## All kinds of mapping cardinalities (1 of 3)

<div class="p-5">


A student can have at most one advisor

<div class="p-5">

```mermaid  {scale: 0.6}
%% Mapping cardinalities: "each student can have at most one advisor"
%% (student 0..1 instructor; instructor 0..many students)
erDiagram
  student {
    int id PK
    string name
    int tot_cred
  }

  instructor {
    int id PK
    string name
    decimal salary
  }

  student }o--|o instructor : advisor

```

</div>

</div>


---

## All kinds of mapping cardinalities (2 of 3)

<div class="p-5">


- An instructor can advise at most one student; a student can have at most one advisor
  - 1:1, optional on both sides

<br>

<div class="pl-5">


```mermaid {scale: 0.6}
%% "All kinds of mapping cardinalities" variant: 1:1 optional on both sides
erDiagram
  student {
    int id PK
    string name
    int tot_cred
  }
  instructor {
    int id PK
    string name
    decimal salary
  }

  student o|--o| instructor : advisor
```

</div>


</div>


---


## All kinds of mapping cardinalities (3 of 3)

<div class="p-5">


- A student can be advised by multiple instructors; an instructor can advise multiple students
  - M:N, optional on both sides

<br>


<div class="pl-5">

```mermaid {scale: 0.6}
%% "All kinds of mapping cardinalities" variant: M:N optional on both sides
erDiagram
  student {
    int id PK
    string name
    int tot_cred
  }
  instructor {
    int id PK
    string name
    decimal salary
  }

  student o{--o{ instructor : advisor
```

</div>

</div>



---

## Crow’s Foot — 1:1

<div class="p-5">



<img src="/images/crow1.png" class="w-120" />


<br>

- optional, and at most 1


</div>


---

## Crow’s Foot — 1:M

<div class="p-5">


<img src="/images/crow2.png"  class="w-120" />

<br>

- Each instructor can advise multiple students.
- Each student may have an advisor (optional).


</div>



---


## Crow’s Foot — M:N

<div class="p-5">


<img src="/images/crow3.png"  class="w-150" />


</div>


---
layout: center
---

<img src="/images/crow.png"  class="w-120" />





---

## Summary

<div class="p-5">

- ER models can be visualized.
- This helps the data designer, and also helps when sharing a model with stateholders.
- One complication is “weak entity sets”.


</div>

