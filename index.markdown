---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
---

<center><h3>UPCOMING UPDATES</h3></center>
<ul>

{% capture now %}{{'now' | date: '%s' | plus: 0 }}{% endcapture %}

{% assign release_dates = site.release_dates %}
{% for release_date in release_dates %}
  {% capture date %}{{release_date.to_date | date: '%s' | plus: 0 }}{% endcapture %}
  {% if date >= now %}
<a href="{{ release_date.url }}"><li class="{{ release_date.type }}"><b>{{ release_date.title}}</b>
<br>{{ release_date.to_date | timeago }}</li></a>
  {% endif %}
{% endfor %}
</ul>

<center><h3>PAST UPDATES</h3></center>
<ul>
{% for release_date in site.release_dates  %}
  {% capture date %}{{release_date.to_date | date: '%s' | plus: 0 }}{% endcapture %}
  {% if date < now %}
	<a href="{{ release_date.url }}"><li class="{{ release_date.type }}"><b>{{ release_date.title}}</b>
	 <br>{{ release_date.to_date | timeago }}</li></a>
  {% endif %}
{% endfor %}
</ul>


<style>
li.worldupdate {
  border: 1px solid #007bff!important;
  background-color: #c1ddfb;
}

li.simupdate {
  border: 1px solid #dc3545!important;
  background-color: #ffb3ba;
}

li.patch {
  border: 1px solid #28a745!important;
  background-color: #cbfbd6;
}

div div p {
  font-size: 0.5rem;
}

li {
  list-style-type: none; /* Remove bullets */
  padding: 0; /* Remove padding */
  margin: 0; /* Remove margins */
  margin: .25rem;
  background-color: #f5f5f5;
  text-align: center;
  padding-top: 5px;
  padding-bottom: 5px;
  padding-right: 5px;
  padding-left: 5px;
  border-radius: 3px;
  color: #434343;
}

</style>