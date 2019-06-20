---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: splash
author_profile: false
classes:
  - landing
header:
  overlay_image: /assets/images/LU-cover-2000x1500.jpg
  overlay_filter: 0.6
  caption: "Credits: [**Stefanie Klamuth**](/authors/kaputtzig/)"
  actions:
    - label: "Jetzt Mitglied werden!"
      url: "/about/"
    - label: "Hier spenden!"
      url: "#"
#title: "assoziation panda! 🐾"
excerpt: "Verein zur Förderung des kritischen literarischen Diskurses"
share: true
---

> Kritische Buchbesprechungen & Buchtipps, Einladungen & Berichte zu unseren **panda lectures** sowie zu anderen Events.

[kritische buchempfehlungen](/books/){: .btn .btn--info .btn--large}
[panda info newsletter](/news/){: .btn .btn--info .btn--large}
[panda lectures & andere events](/events/){: .btn .btn--info .btn--large}
<!-- [panda podcasts](/podcasts/){: .btn .btn--info .btn--large} -->
[und mehr …](/about/){: .btn .btn--info .btn--large}

<!--
**B&nbsp;E&nbsp;&nbsp; &nbsp;R&nbsp;A&nbsp;D&nbsp;I&nbsp;C&nbsp;A&nbsp;L&nbsp;&nbsp;** 🐾 **&nbsp;&nbsp;R&nbsp;E&nbsp;A&nbsp;D&nbsp;&nbsp; &nbsp;B&nbsp;O&nbsp;O&nbsp;K&nbsp;S&nbsp;&nbsp;** 📕
{: .text-center}
{: .notice--danger}
-->

{% capture written_label %}'None'{% endcapture %}

{% for collection in site.collections %}
  {% unless collection.output == false or collection.label == "posts" %}
    {% capture label %}{{ collection.label }}{% endcapture %}
    {% if label != written_label %}
<h2 id="{{ label | slugify }}" class="archive__subtitle">{{ label }}</h2>
      {% capture written_label %}{{ label }}{% endcapture %}
    {% endif %}
  {% endunless %}
  {% for post in collection.docs %}
    {% unless collection.output == false or collection.label == "posts" %}
      {% include archive-single.html %}
    {% endunless %}
  {% endfor %}
{% endfor %}
