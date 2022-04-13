---
---
# Welcome to the FOSS Pod Community Wiki!

This is a community wiki for [Brad and Will Present a FOSS Pod](https://fosspod.content.town),
a biweekly podcast about the Free and Open Source Software (FOSS) that’s changing the world, and the developers who are making it happen.

![FOSSPod Logo](images/fosspod-logo.jpg)

This Wiki is hosted on [Github:
FOSSPod-wiki](https://github.com/TurboSB/FOSSPod-wiki) See [README](README.md)
for detail documentation.

Any suggestions and comments, use the [Issue Tracker](https://github.com/TurboSB/FOSSPod-wiki/issues)

## Episodes
### Season 1
<ol>
{% for episode in site.tags.season-1 %}
  <li>
    <a href="{{ episode.url }}">
      {{ episode.title }}
    </a>
  </li>
{% endfor %}
</ol>

## Show Sponsors
[Google Open Source](opensource.google)

## Helpful Lists of FOSS packages
[Wikipedia](https://en.wikipedia.org/wiki/List_of_free_and_open-source_software_packages)

[episodelist](episode-list.md)