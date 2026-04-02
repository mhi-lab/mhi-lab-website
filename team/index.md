---
title: Team
nav:
  order: 3
  tooltip: About our team
---

# {% include icon.html icon="fa-solid fa-users" %}Team

text..

{% include section.html %}

## Principal Investigator
{% include list.html data="members" component="portrait" filter="role == 'principal-investigator'" %}

## PhD Students
{% include list.html data="members" component="portrait" filter="role != 'principal-investigator'" %}
