---
---
# Episode List

{% assign page_tags = "" | split: ',' %}

{%- for episode in site.episodes -%}
  {% assign page_tags = page_tags | push: episode.season %}
{%- endfor -%}

{% assign sortedtags = page_tags | uniq | sort%}

{% for tag in sortedtags %}
  {% assign all_tagged = "" | split: ',' %}

  <h2 id="Season {{ tag }}">Season {{ tag }}</h2>
  <ol>

  {% comment %}
  # combine posts and pages with this tag
  {% endcomment %}

  {% for episode in site.episodes %}
    {% if episode.season = tag %}
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