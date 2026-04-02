---
title: Contact
nav:
  order: 5
  tooltip: Email, address, and location
---

# {% include icon.html icon="fa-regular fa-envelope" %}Contact

Text

{%
  include button.html
  type="email"
  text="cchen@eee.hku.hk"
  link="cchen@eee.hku.hk"
%}
{%
  include button.html
  type="phone"
  text="(555) 867-5309"
  link="+1-555-867-5309"
%}
{%
  include button.html
  type="address"
  tooltip="Our location on Google Maps for easy navigation"
  link="https://maps.app.goo.gl/nnCx2daMn2eTN9Pi9"
%}

<div style="margin-top: 40px; margin-bottom: 40px; width: 100%;">
  <iframe 
    src="https://maps.google.com/maps?q=The+University+of+Hong+Kong,+Pokfulam,+Hong+Kong&t=&z=15&ie=UTF8&iwloc=&output=embed" 
    width="100%" 
    height="450" 
    style="border: 0; border-radius: 10px; box-shadow: 0 4px 12px rgba(0,0,0,0.1);" 
    allowfullscreen="" 
    loading="lazy" 
    referrerpolicy="no-referrer-when-downgrade">
  </iframe>
</div>

{% include section.html %}

{% comment %}
{% include section.html %}

{% capture col1 %}

{%
  include figure.html
  image="images/photo.jpg"
  caption="Lorem ipsum"
%}

{% endcapture %}

{% capture col2 %}

{%
  include figure.html
  image="images/photo.jpg"
  caption="Lorem ipsum"
%}

{% endcapture %}

{% include cols.html col1=col1 col2=col2 %}

{% include section.html dark=true %}

{% capture col1 %}
Lorem ipsum dolor sit amet  
consectetur adipiscing elit  
sed do eiusmod tempor
{% endcapture %}

{% capture col2 %}
Lorem ipsum dolor sit amet  
consectetur adipiscing elit  
sed do eiusmod tempor
{% endcapture %}

{% capture col3 %}
Lorem ipsum dolor sit amet  
consectetur adipiscing elit  
sed do eiusmod tempor
{% endcapture %}

{% include cols.html col1=col1 col2=col2 col3=col3 %}

{% endcomment %}
