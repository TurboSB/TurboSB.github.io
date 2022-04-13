---
---
# Episode List

{% assign page_tags = "" | split: ',' %}

{%- for episode in site.episodes -%}
  {% assign page_tags = page_tags | concat:episode.tags %}
{%- endfor -%}

{% assign sortedtags = page_tags | uniq | sort%}

{% for tag in sortedtags %}
  {% assign all_tagged = "" | split: ',' %}

  <h2 id="{{ tag }}">{{ tag }}</h3>
  <ol>

  {% comment %}
  # combine posts and pages with this tag
  {% endcomment %}

  {% for episode in site.episodes %}
    {% if episode.tags contains tag %}
      {% assign all_tagged = all_tagged | push: episode %}
    {% endif %}
  {% endfor %}

  {% comment %}
  # sort by title
  {% endcomment %}
  {% assign all_tagged = all_tagged | sort: "title" %}


  {% comment %}
  # finally, print the list item!
  {% endcomment %}
  {% for tagged in all_tagged %}
    <li><a href="{{ tagged.url }}">{{ tagged.title }}</a></li>
  {% endfor %}

  </ol>
{% endfor %}