---
title: Team
nav:
  order: 2
  tooltip: About our team
---

<div class="team-page">

<h2>Principal Investigator</h2>

{% include list.html data="members" component="portrait" filter="role == 'principal-investigator'" %}

<h2>PhD Students</h2>

{% include list.html data="members" component="portrait" filter="role != 'principal-investigator'" %}

</div>
