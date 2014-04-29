---
layout: frontpage
title: Strong Naming Considered Harmful
tagline: Strong naming bad. Free your bits.
---

{% for faq in site.data.faq %}

  {% comment %}
    Somehow the Liquid filter 'handleize' does not work in Jekyll/GitHub Pages.
    So below is a very simple hack to get some kind of "handle" from a raw
    question string.
  {% endcomment %}
  {% assign handlized = faq.question | strip | downcase | replace:' ','-' %}
  
  <h3><a name="{{ handlized }}" class="anchor" href="#{{ handlized }}"><span class="octicon octicon-link"></span></a>
  {{ faq.question }}
  </h3>

  {{ faq.answer }}

{% endfor %}
