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
  link="https://maps.app.goo.gl/jjB8hG69p2PYC5Vc8"
%}

<div style="margin-top: 40px; margin-bottom: 40px; width: 100%;">
  <iframe 
    src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3691.865240218691!2d114.13398717605006!3d22.283094043517412!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x3403ff8427b43597%3A0x2c48f5d3cd6fc8d8!2sThe%20University%20of%20Hong%20Kong%20(HKU)!5e0!3m2!1sen!2stw!4v1775156541153!5m2!1sen!2stw" 
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
