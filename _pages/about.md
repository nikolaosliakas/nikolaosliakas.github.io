---
title: "About"
layout: homelay
description: "Nikos Liakas - Software Engineer"
permalink: /
---

<pre class="ascii-art glow-pulse" aria-hidden="true">
 ___   __       ________     ___   ___     ______      ______         
/__/\ /__/\    /_______/\   /___/\/__/\   /_____/\    /_____/\        
\::\_\\  \ \   \__.::._\/   \::.\ \\ \ \  \:::_ \ \   \::::_\/_       
 \:. `-\  \ \     \::\ \     \:: \/_) \ \  \:\ \ \ \   \:\/___/\      
  \:. _    \ \    _\::\ \__   \:. __  ( (   \:\ \ \ \   \_::._\:\     
   \. \`-\  \ \  /__\::\__/\   \: \ )  \ \   \:\_\ \ \    /____\:\    
    \__\/ \__\/  \________\/    \__\/\__\/    \_____\/    \_____\/    
 __          ________     ________      ___   ___     ________      ______     
/_/\        /_______/\   /_______/\    /___/\/__/\   /_______/\    /_____/\    
\:\ \       \__.::._\/   \::: _  \ \   \::.\ \\ \ \  \::: _  \ \   \::::_\/_   
 \:\ \         \::\ \     \::(_)  \ \   \:: \/_) \ \  \::(_)  \ \   \:\/___/\  
  \:\ \____    _\::\ \__   \:: __  \ \   \:. __  ( (   \:: __  \ \   \_::._\:\ 
   \:\/___/\  /__\::\__/\   \:.\ \  \ \   \: \ )  \ \   \:.\ \  \ \    /____\:\
    \_____\/  \________\/    \__\/\__\/    \__\/\__\/    \__\/\__\/    \_____\/
</pre>

<!-- ═══════════ ABOUT TAB ═══════════ -->
<div class="content-tab-panel active" id="tab-about">

<div class="section-prompt">
<span class="dollar">$</span> <span class="cmd">whoami</span>
</div>

<div class="cmd-output stagger-children">
{% for member in site.data.pi %}
<p><span class="output-line" style="color: var(--text-primary); font-weight: 600; font-size: 1.2rem;">{{ member.name }}</span>
<span class="output-line" style="color: var(--amber);">{{ member.info }}</span>
</p>

<div style="display: flex; align-items: flex-start; gap: 1.5rem; flex-wrap: wrap; margin: 1rem 0;">
<img src="{{ site.url }}{{ site.baseurl }}/images/teampic/{{ member.photo }}" alt="{{ member.name }}" style="width: 130px; height: 130px; border-radius: 50%; border: 2px solid var(--green); object-fit: cover;">
<div style="font-size: 0.95rem; line-height: 1.8;">
<span style="color: var(--text-muted);">📧</span> <a href="mailto:{{ member.email }}">{{ member.email }}</a><br>
<span style="color: var(--text-muted);">🐙</span> <a href="{{ member.github }}" target="_blank">GitHub</a><br>
<span style="color: var(--text-muted);">💼</span> <a href="{{ member.linkedin }}" target="_blank">LinkedIn</a>
</div>
</div>
{% endfor %}
</div>

<div class="section-prompt">
<span class="dollar">$</span> <span class="cmd">tree ~/work_and_education</span>
</div>

{% for member in site.data.pi %}
<div class="tree stagger-children">
{% for educ in (1..member.number_educ) %}
{% assign start_key = "education" | append: educ | append: "_start" %}
{% assign end_key = "education" | append: educ | append: "_end" %}
{% assign detail_key = "education" | append: educ | append: "_detail" %}
<div class="tree-item">
{% assign short_key = "education" | append: educ | append: "short" %}
<span class="tree-date" {% if member[start_key] %}data-start="{{ member[start_key] }}"{% endif %} {% if member[end_key] %}data-end="{{ member[end_key] }}"{% endif %}>{{ member[short_key] }}</span>
<span class="tree-label">{% if member[detail_key] %}<br><span style="color: var(--text-muted); font-size: 0.9rem;">{{ member[detail_key] }}</span>{% endif %}</span>
</div>
{% endfor %}
</div>
{% endfor %}

<div class="section-prompt" style="margin-top: 2rem;">
<span class="dollar">$</span> <span class="cmd">cat about.md</span>
</div>

<div class="about-text" style="color: var(--text-secondary); line-height: 1.8; max-width: 75ch;">

I am transitioning from data engineering of financial models to C++ Software Engineer. Having recently completed my MSc in Computer Science, I have unique blend of both more than four years experience in the hands-on design, planning, implementation and testing of software, as well as the academic and research background of in infrastructure aware development. 

___

My interests are compiler design, hacking memory allocators and static analysis. This is combined with multiple [projects](https://nikolaosliakas.github.io/software/) in C++ and OCaml. 

</div>

</div>

<!-- ═══════════ NEWS TAB ═══════════ -->
<div class="content-tab-panel" id="tab-news">

<div class="section-prompt">
<span class="dollar">$</span> <span class="cmd">tail -5 ~/news.log</span>
</div>

<div class="stagger-children">
{% for article in site.data.news limit:10 %}
<div class="news-item" style="margin-bottom: 1.5rem; padding-left: 1rem; border-left: 2px solid var(--border);">
<span style="color: var(--amber); font-size: 0.85rem;">{{ article.date }}</span>
<p style="margin: 0.25rem 0 0;">{{ article.headline }}</p>
{% if article.images %}
<div class="image-gallery" style="display: flex; gap: 0.5rem; margin-top: 0.5rem; flex-wrap: wrap;">
{% for image in article.images %}
<a href="#" data-full="{{ site.url }}{{ site.baseurl }}/images/{{ image }}">
<img src="{{ site.url }}{{ site.baseurl }}/images/{{ image }}" alt="Photo" style="height: 80px; border-radius: 4px; border: 1px solid var(--border); cursor: pointer;">
</a>
{% endfor %}
</div>
{% endif %}
</div>
{% endfor %}
</div>

<p style="margin-top: 1rem;"><a href="{{ site.baseurl }}/allnews.html">→ all news</a></p>

</div>

<!-- ═══════════ STUDENTS TAB ═══════════ -->
<!-- <div class="content-tab-panel" id="tab-students">

<div class="section-prompt">
<span class="dollar">$</span> <span class="cmd">ls ~/supervised-students/</span>
</div>

<div class="tree stagger-children">
<div class="tree-item">
<span class="tree-date">2024</span>
<span class="tree-label">Student Name — <a href="#">Thesis Title</a></span>
</div>
<div class="tree-item">
<span class="tree-date">2023</span>
<span class="tree-label">Student Name — <a href="#">Project Title</a></span>
</div>
</div>

</div> -->

<!-- ═══════════ PERSONAL TAB ═══════════ -->
<div class="content-tab-panel" id="tab-personal">

<div class="section-prompt">
<span class="dollar">$</span> <span class="cmd">cat ~/personal.md</span>
</div>

<style>
  .book-title strong {
    color: #33fff8; 
  }
</style>

<div class="book-title" style="color: var(--text-secondary); line-height: 1.8; margin-bottom: 2rem;">

I like to read literature, history, poetry and philosophy when not pinning pointers to addresses. Running and climbing especially with friends. Baile funk, laouto, paixnidia etc etc.

____

Highlight reads, unsorted:

- **The Information** by James Gleick
- **2666** by Roberto Bolano
- **By Grand Central Station I Sat Down and Wept** by Elizabeth Smart
- **Event** by Slavoj Zizek
- **The Autobiography of Red** by Anne Carson

</div>

<div class="section-prompt" style="margin-top: 2rem;">
<span class="dollar">$</span> <span class="cmd">cat ~/places/map.svg</span>
</div>

<div id="places-map" style="height: 350px; border: 1px solid var(--border); border-radius: 6px; margin: 1rem 0; z-index: 0;"></div>

<div class="section-prompt" style="margin-top: 1.5rem;">
<span class="dollar">$</span> <span class="cmd">tree ~/places --timeline</span>
</div>

<div class="tree stagger-children">
<div class="tree-item">
<span class="tree-date" data-start="1991-01" data-end="2013-06" style="min-width: 80px;">0 – 21</span>
<span class="tree-label">🏠 <a href="https://en.wikipedia.org/wiki/Toronto">Toronto</a>, Canada</span>
</div>
<div class="tree-item">
<span class="tree-date" data-start="2016-06" style="min-width: 80px;">25 – now</span>
<span class="tree-label">🏙️ <a href="https://en.wikipedia.org/wiki/London">London</a>, United Kingdom</span>
</div>
</div>

</div>
