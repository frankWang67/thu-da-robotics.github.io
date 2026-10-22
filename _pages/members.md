---
layout: profiles
permalink: /members/
title: Members
nav: true
nav_order: 7
profiles:
  - align: right
    image: people/lixiang.avif
    image_circular: false # crops the image to make it circular
---

{% include_relative about_xiangli.md %}

<div style="clear: both;"></div>

{% for group in site.data.members %}
{% if group.list.size > 0 %}
<br>
{% if group.name %}

<h2>{{ group.name }}</h2>
    {% endif %}
    {% if group.full %}
<div style="margin-bottom: 0.5rem;"></div>
<div class="row">
      {% for member in group.list %}
<div class="col-sm-4 col-md-3 text-center" style="width: 50%;">
        {% if member.website %}
<a href="{{ member.website }}" target="_blank" rel="noopener noreferrer">
{% include figure.liquid loading="eager" path=member.image alt=member.alt class="img-fluid rounded" %}
</a>
        {% else %}
          {% include figure.liquid loading="eager" path=member.image alt=member.alt class="img-fluid rounded" %}
        {% endif %}
<p style="margin-bottom: 1.5rem;">{{ member.name }}</p>
</div>
      {% endfor %}
</div>
    {% else %}
<ul>
      {% for member in group.list %}
<li>
        {% if member.website %}
<a href="{{ member.website }}" target="_blank" rel="noopener noreferrer">{{ member.name }}</a>
        {% else %}
          {{ member.name }}
        {% endif %}
</li>
      {% endfor %}
</ul>
    {% endif %}
  {% endif %}
{% endfor %}
