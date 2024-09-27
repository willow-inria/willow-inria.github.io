---
layout: page
permalink: /team/
title: Team
nav: true
nav_order: 2
---


<h3 class="faculty" align="right">Faculty</h3>
<div class="team">
{% assign names_sorted = "" | split: ',' %}
{% for member in site.data.team %}
  {% if member[1].type == "faculty" %}
    {% assign names_sorted = names_sorted | push: member[0] %}
  {% endif %}
{% endfor %}
{% assign names_sorted = names_sorted | sort_natural %}
{% for name in names_sorted %}
    {% assign member = "" | split: ',' | push: name | push: site.data.team[name] %}
    {% include team/member.liquid member=member %}
{% endfor %}
</div>


<br>
<h3 class="students" align="right">Project Managers and Assistants</h3>
<div class="team">
{% assign names_sorted = "" | split: ',' %}
{% for member in site.data.team %}
  {% if member[1].type == "staff" %}
    {% assign names_sorted = names_sorted | push: member[0] %}
  {% endif %}
{% endfor %}
{% assign names_sorted = names_sorted | sort_natural %}
{% for name in names_sorted %}
    {% assign member = "" | split: ',' | push: name | push: site.data.team[name] %}
    {% include team/member.liquid member=member %}
{% endfor %}
</div>


<br>
<h3 class="students" align="right">Postdocs and Engineers</h3>
<div class="team">
{% assign names_sorted = "" | split: ',' %}
{% for member in site.data.team %}
  {% if member[1].type == "postdoc/engineer" %}
    {% assign names_sorted = names_sorted | push: member[0] %}
  {% endif %}
{% endfor %}
{% assign names_sorted = names_sorted | sort_natural %}
{% for name in names_sorted %}
    {% assign member = "" | split: ',' | push: name | push: site.data.team[name] %}
    {% include team/member.liquid member=member %}
{% endfor %}
</div>

<br>
<h3 class="students" align="right">Students</h3>
<div class="team">
{% assign names_sorted = "" | split: ',' %}
{% for member in site.data.team %}
  {% if member[1].type == "student" %}
    {% assign names_sorted = names_sorted | push: member[0] %}
  {% endif %}
{% endfor %}
{% assign names_sorted = names_sorted | sort_natural %}
{% for name in names_sorted %}
    {% assign member = "" | split: ',' | push: name | push: site.data.team[name] %}
    {% include team/member.liquid member=member %}
{% endfor %}
</div>


<br>
<h3 class="visitors" align="right">Visitors</h3>
<div class="team">
{% assign names_sorted = "" | split: ',' %}
{% for member in site.data.team %}
  {% if member[1].type == "visitor" %}
    {% assign names_sorted = names_sorted | push: member[0] %}
  {% endif %}
{% endfor %}
{% assign names_sorted = names_sorted | sort_natural %}
{% for name in names_sorted %}
    {% assign member = "" | split: ',' | push: name | push: site.data.team[name] %}
    {% include team/member.liquid member=member %}
{% endfor %}
</div>

<br>
<br>
<br>
<h2 class="former-members" align="right">Former members</h2>

{% include former_members.liquid %}

<h2 class="former-visitors" align="right">Former Visitors</h2>

{% include former_visitors.liquid %}
