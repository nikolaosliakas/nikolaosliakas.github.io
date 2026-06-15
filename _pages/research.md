---
title: "Research"
layout: gridlay
description: "Your research projects and interests."
sitemap: true
permalink: /research
---

<div class="section-prompt">
<span class="dollar">$</span> <span class="cmd">cat research.txt</span>
</div>

<div style="color: var(--text-secondary); line-height: 1.8; max-width: 75ch; margin-bottom: 2rem;">

My research focuses on three areas in Computer Science:

1. Memory Allocators
2. Metaprogramming
3. Static Analysis

</div>

<div class="section-prompt">
<span class="dollar">$</span> <span class="cmd">ls -la ~/projects/</span>
</div>

### **LCSTRS_of_ocaml**: A translator from OCaml to LCSTRS for termination analysis 

<div style="color: var(--text-secondary); line-height: 1.8; margin-bottom: 2rem;">

My master's thesis was a program and a report on using *Logically Constrained Simply-typed Term Rewrite Systems* (LCSTRS) for analysis of program termination. This involved using OCaml's `ppxlib` a pre-processing library to retrieve the intermediary representation (IR) of compiled OCaml source code and through a simplified compilation process translate it to LCSTRS representation.

The expression that was output would be input into a collection of SAT solvers and theorum provers to determine if a program would terminate on all inputs. 

<!-- - [GitHub repo](https://github.com/yourusername/project) -->
- [Thesis PDF](papers/msc_proj_report.pdf)

</div>
