---
---
# Episode List

## Season 1


{% for tag in site.tags %}
  {% assign t = tag | first %}
  {% assign episodes = tag | last %}

  {{ t | downcase }}
  <ol>
    {% for episode in episodes %}
      {% if episode.tags contains t %}
      <li>
        <a href="{{ episode.url }}">
          {{ episode.title }}
        </a>
      </li>
      {% endif %}
    {% endfor %}
  </ol>
{% endfor %}