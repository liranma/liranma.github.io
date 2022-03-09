---
layout: archive
title: "Publications"
permalink: /publications/
author_profile: true
---

You can find my articles on my <a href="https://scholar.google.com/citations?hl=en&user=bHajvFMAAAAJ" target="_blank">Google Scholar profile</a>.

{% if author.googlescholar %}
  You can also find my articles on <u><a href="{{author.googlescholar}}">my Google Scholar profile</a>.</u>
{% endif %}

{% include base_path %}

{% for post in site.publications reversed %}
  {% include archive-single.html %}
{% endfor %}
