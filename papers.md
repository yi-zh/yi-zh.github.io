---
layout: photolist
title: Publications
description: Publications with links to papers, blogs and code.
menu: no
order: 2
---

{% assign hashes = (site.data.papers) %}
{% capture years %}
{% for hash in hashes %}
{{ hash[0] }}
{% endfor %}
{% endcapture %}

{% assign sortedyears = years | split:' ' | sort | reverse %}
{% for year in sortedyears %}
[comment]: <> (### {{ year }})
{% for paper in hashes[year] %}
{% include paper_in_box_wide.html paper=paper %}
{% endfor %}
{% endfor %}