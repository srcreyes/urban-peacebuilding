---
layout: default
title: Urban Peacebuilding Sites Observatory
header_type: hero
subtitle: Urban peacebuilding in a spatial context
---

Spatial peacebuilding highlights the agency of places and spaces that promote peace or reinforce conflict in conflict-affected societies. This paper draws on the growing literature on spatial peacebuilding in an urban context to analyze the post-siege reconstruction of Marawi City. In 2017, Marawi City witnessed a five-month battle between Islamic militant groups and the Philippine military, resulting in the longest urban warfare in the country. The aftermath of the siege saw more than a thousand people dead, thousands more injured, and hundreds of thousands became refugees in neighboring provinces. The government has launched an inter-agency reconstruction effort, but the ruins of residential houses, commercial buildings, and places of worship have become fixtures of the new urbanscape of Marawi City. This pre-fieldwork paper explores the potential peace-promoting and conflict-reinforcing agencies of urban spaces and places in the reconstruction of Marawi City. This exploration aims to contribute an urban perspective to spatial peacebuilding scholarship and inform national/subnational policies for rebuilding Marawi City.

<!DOCTYPE html>
<html dir="ltr" lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <title>{{ site.title }}</title>
	<meta name="keywords" content="{{ site.keywords }}">
	<meta name="description" content="{{ site.description }}">
  <link rel="stylesheet" href="combo.css">
  <link href='http://fonts.googleapis.com/css?family=Raleway:400,300,700' rel='stylesheet' type='text/css'>
  <link rel="stylesheet" href="//netdna.bootstrapcdn.com/font-awesome/4.2.0/css/font-awesome.min.css">
  {% if site.favicon %}<link rel="shortcut icon" href="{{ site.favicon }}" type="image/x-icon">{% endif %}
	{% if site.touch_icon %}<link rel="apple-touch-icon" href="{{ site.touch_icon }}">{% endif %}
</head>
<body>
  <div id="main">

    <nav><ul>
      {% for node in site.posts reversed %}
        {% capture id %}{{ node.id | remove:'/' | downcase }}{% endcapture %}
        <li class="p-{{id}}"><a href="#{{id}}">{{node.title}}</a></li>
      {% endfor %}
    </ul></nav>


    {% for page in site.posts reversed %}
      {% capture id %}{{ page.id | remove:'/' | downcase }}{% endcapture %}
      <div id="{{id}}" class="section p-{{id}}">
        {% if page.icon %}
        <div class="subtlecircle sectiondivider imaged">
          <img src="{{page.icon}}" alt="section icon" />
          <h5 class="icon-title">{{ page.title }}</h5>
        </div>
        {% elsif page.fa-icon %}
        <div class="subtlecircle sectiondivider faicon">
          <span class="fa-stack">
            <i class="fa fa-circle fa-stack-2x"></i>
            <i class="fa fa-{{ page.fa-icon }} fa-stack-1x"></i>
          </span>
          <h5 class="icon-title">{{ page.title }}</h5>
        </div>
        {% endif %}
        <div class="container {{ page.style }}">
          {{ page.content }}
        </div>
      </div>
    {% endfor %}


    <div id="footer" class="section text-white">
      <div class="container">
        {% capture foottext %} {% include footer.md %} {% endcapture %}
        {{ foottext | markdownify }}
      </div>
    </div>
  </div>

{% include analytics.html %}
</body>
<script src="//ajax.googleapis.com/ajax/libs/jquery/2.1.1/jquery.min.js"></script>
<script src="site.js"></script>
</html>
