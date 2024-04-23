---
layout: page
permalink: /publications/
title: papers
description: 
start_year: 2021
nav: true
nav_order: 2
---
<!-- _pages/publications.md -->

<script type='text/javascript' src='https://d1bxh8uas1mnw7.cloudfront.net/assets/embed.js'></script>
<script async src="https://badge.dimensions.ai/badge.js" charset="utf-8"></script>
\* denotes equal contribution
<div class="publications">

{% assign now = 'now' | date: "%Y" %}
{% for y in (page.start_year..now) reversed %}
  {% capture bib_count %}{% bibliography_count -f papers -q @*[year={{y}}]* %}{% endcapture %}
  {% assign bib_count = bib_count | to_integer %}
  {% if bib_count > 0 %}
  {% bibliography -f papers -q @*[year={{y}}]* %}
  {% endif %}
{% endfor %}

</div>
