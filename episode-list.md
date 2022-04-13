# Episode List

## Season 1

<ol>
{% for episode in site.tags.tag %}
  <li>
    <a href="{{ episode.url }}">
      {{ episode.title }}
    </a>
  </li>
{% endfor %}
</ol>
