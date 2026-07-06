---
layout: single
permalink: /publications/
---

<div class="section-head reveal"><h2>All Publications</h2><span class="bar"></span><span class="more">{{ site.publications | size }} papers &middot; newest first</span></div>
<section class="rows">
  {% assign all = site.publications | sort: "date" | reverse %}
  {% for p in all %}
  {% assign rlink = p.paperurl | default: p.webpage | default: p.pdf | default: p.code %}
  <div class="prow reveal">
    {% if p.teaser %}<div class="rthumb"><img src="{{ p.teaser | relative_url }}" alt=""></div>
    {% else %}<div class="rthumb ph"><span>image</span></div>{% endif %}
    <div class="rbody">
      <p class="rmeta">{{ p.venue }}{% if p.date %} &middot; {{ p.date | date: "%Y" }}{% endif %}</p>
      <h3 class="rtitle">{% if rlink %}<a href="{{ rlink }}" target="_blank" rel="noopener">{{ p.title }}</a>{% else %}{{ p.title }}{% endif %}</h3>
      {% if p.authors %}<p class="rauth">{{ p.authors }}</p>{% endif %}
      <div class="publinks">
        {% if p.bibtex %}<button class="plink" data-bib="bib-{{ forloop.index }}">BibTeX</button>{% endif %}
        {% if p.paperurl %}<a class="plink" href="{{ p.paperurl }}">DOI</a>{% endif %}
        {% if p.pdf %}<a class="plink" href="{{ p.pdf }}">PDF</a>{% endif %}
        {% if p.code %}<a class="plink" href="{{ p.code }}">Code</a>{% endif %}
        {% if p.webpage %}<a class="plink" href="{{ p.webpage }}">Webpage</a>{% endif %}
        {% if p.video %}<a class="plink" href="{{ p.video }}">Video</a>{% endif %}
        {% if p.slides %}<a class="plink" href="{{ p.slides }}">Slides</a>{% endif %}
        {% if p.projectpage %}<a class="plink plink-proj" href="{{ p.projectpage }}">Project Page</a>{% endif %}
      </div>
      {% if p.bibtex %}<div class="bibtex" id="bib-{{ forloop.index }}" hidden><span class="copy">Copy</span><code>{{ p.bibtex }}</code></div>{% endif %}
    </div>
  </div>
  {% endfor %}
</section>