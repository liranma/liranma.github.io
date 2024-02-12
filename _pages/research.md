---
layout: archive
title: "Research"
permalink: /research/
author_profile: true
---

You can find my articles on my <a href="https://scholar.google.com/citations?hl=en&user=bHajvFMAAAAJ" target="_blank">Google Scholar profile</a>. 

We have developed a number of hands-on labs for better understanding cybersecurity concepts and technologies, which is available at <a href="https://eurekalabs.net/" target="_blank">Eureka Labs</a>.

{% if author.googlescholar %}
  You can also find my articles on <u><a href="{{author.googlescholar}}">my Google Scholar profile</a>.</u>
{% endif %}

{% include base_path %}

{% for post in site.publications reversed %}
  {% include archive-single.html %}
{% endfor %}
