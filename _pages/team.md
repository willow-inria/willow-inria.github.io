---
layout: page
permalink: /team/
title: Team
nav: true
nav_order: 2
---

<!-- pages/team.md -->
<!-- sort active members -->
{% assign names_sorted = "" | split: ',' %}
{% for member in site.data.team %}
  {% if member[1].alumni != true %}
    {% if member[1].permanent == true %}
      {% assign names_sorted = names_sorted | push: member[0] %}
    {% endif %}
  {% endif %}
{% endfor %}
{% assign names_sorted = names_sorted %}

<h3 class="faculty" align="right">Faculty</h3>
<div class="team">
{% for name in names_sorted %}
    {% assign member = "" | split: ',' | push: name | push: site.data.team[name] %}
    {% include team/member.liquid member=member %}
{% endfor %}
</div>


{% assign names_sorted = "" | split: ',' %}
{% for member in site.data.team %}
  {% if member[1].alumni != true %}
    {% if member[1].permanent != true %}
      {% assign names_sorted = names_sorted | push: member[0] %}
    {% endif %}
  {% endif %}
{% endfor %}
{% assign names_sorted = names_sorted | sort_natural %}

<br>
<h3 class="students" align="right">Postdocs and students</h3>
<div class="team">
{% for name in names_sorted %}
    {% assign member = "" | split: ',' | push: name | push: site.data.team[name] %}
    {% include team/member.liquid member=member %}
{% endfor %}
</div>

<!-- display Alumni in their data listing order -->
<!-- could not manage to sort by alumni_date since Liquid does not allow modifying object w/o use of a plugin -->
<br>
<br>
<br>
<h2 class="alumni" align="right">Alumni</h2>
<div class="team alumni">
{% for member in site.data.team %}
  {% if member[1].alumni == true %}
    {% include team/member.liquid member=member %}
  {% endif %}
{% endfor %}
</div>
