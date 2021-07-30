---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
---

<h2> Upcoming: </h2>
<ul>
{% capture now %}{{'now' | date: '%s' | plus: 0 }}{% endcapture %}
{% for release_date in site.release_dates %}
  {% capture date %}{{release_date.to_date | date: '%s' | plus: 0 }}{% endcapture %}
  {% if date > now %}
	<li><a href="{{ release_date.url }}">{{ release_date.title}}</a> - {{ release_date.to_date | timeago }}</li>
  {% endif %}
{% endfor %}
</ul>

<h2> Past: </h2>

<ul>
{% capture now %}{{'now' | date: '%s' | plus: 0 }}{% endcapture %}
{% for release_date in site.release_dates %}
  {% capture date %}{{release_date.to_date | date: '%s' | plus: 0 }}{% endcapture %}
  {% if date < now %}
<li><a href="{{ release_date.url }}">{{ release_date.title}}</a> - {{ release_date.to_date | timeago }}</li>
  {% endif %}
{% endfor %}
</ul>