---
layout: single
title: "Cours au collège"
permalink: /college/cours.html
toc: true
toc_sticky: true
toc_label: "Chapitres"
toc_levels: 1..6
toc_icon: ""
sidebar:
  nav: "college"
---

{% assign cptfc = 1 %}
{% assign cpthp = 1 %}
{% assign cpttop = 1 %}
{% assign cpttheme = 1 %}

<ul start="1" style="list-style-type:none">
{% for chap in site.data.college.college_cours.chapitres %}
{% assign number = forloop.index | plus: 0 %}
{% if number < 10 %}
{% assign number = "0" | append:number %}
{% endif %}
  
<li>
{% if chap.chapitre %}
<h2 class="mycss" id="chap_{{number}}"><a href="../_pages/college/college-chap{{number}}.pdf">{{number}} - {{chap.titre}}</a></h2>
{% endif %}

{% if chap.td %}
<a href="./exercices/college-chap{{number}}.pdf">Exercices</a>
{%if chap.tdsol%},{%else%}.{%endif%}
{% endif %}

{% if chap.tdsol %}
<a href="./exercices/college-exos_s{{number}}.pdf">Solutions</a>.
{% endif %}
</li>
{% endfor %}
</ul>
