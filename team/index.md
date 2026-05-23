---
title: Team
nav:
  order: 3
  tooltip: About our team
---

## Principal Investigator
{% include list.html data="members" component="portrait" filter="role == 'principal-investigator'" %}

## PhD Students
{% include list.html data="members" component="portrait" filter="role != 'principal-investigator'" %}
