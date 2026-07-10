---
layout: clean
permalink: /publications/
---

{% assign featured = site.publications | sort: "date" | reverse %}
{% if featured.size > 0 %}
<div class="section-head reveal"><h2>Publications</h2><span class="bar"></span></div>
<section class="grid">
  {% for p in featured %}
  {% assign flink = p.paperurl | default: p.webpage | default: p.pdf | default: p.code %}
  <article class="card reveal">
    {% if p.teaser %}<div class="thumb"><img src="{{ p.teaser | relative_url }}" alt=""></div>
    {% else %}<div class="thumb ph"><span>representative image</span></div>{% endif %}
    <div class="body">
      <p class="venue">{{ p.venue }}{% if p.date %} &middot; {{ p.date | date: "%Y" }}{% endif %}</p>
      <h3 class="title">{% if flink %}<a href="{{ flink }}" target="_blank" rel="noopener">{{ p.title }}</a>{% else %}{{ p.title }}{% endif %}</h3>
      {% if p.authors %}<p class="authors">{{ p.authors }}</p>{% endif %}
    </div>
  </article>
  {% endfor %}
</section>
{% endif %}
