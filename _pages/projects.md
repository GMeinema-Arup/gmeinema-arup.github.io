---
layout: archive
title: "Projects"
permalink: /projects/
author_profile: true
---

<h1 class="page-title">Projects</h1>
<p class="lead">
Bridge engineering, computational design, research and educational projects.
</p>

{% assign groups = "professional,prototypes" | split: "," %}
{% assign labels = "Professional Practice,Research & Educational Projects" | split: "," %}

{% for g in groups %}
  {% assign items = site.data.projects[g] %}

  {% if items and items.size > 0 %}

  <div class="section-head">
    <h2>{{ labels[forloop.index0] }}</h2>
  </div>

  <section class="grid projects">

    {% for it in items %}

    <article class="card">

      <div class="thumb">
        {% if it.url %}
          {{ it.url }}
        {% endif %}

        {{ it.image | relative_url }}

        {% if it.url %}
          </a>
        {% endif %}
      </div>

      <div class="body">

        <p class="venue">
          {{ it.org }}
          {% if it.year %}
            &middot; {{ it.year }}
          {% endif %}
        </p>

        <h3 class="title">
          {% if it.url %}
            {{ it.url }}{{ it.title }}</a>
          {% else %}
            {{ it.title }}
          {% endif %}
        </h3>

        {% if it.location %}
          <p class="ploc">{{ it.location }}</p>
        {% endif %}

        {% if it.description %}
          <p class="pdesc">{{ it.description }}</p>
        {% endif %}

      </div>

    </article>

    {% endfor %}

  </section>

  {% endif %}

{% endfor %}