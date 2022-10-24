---
layout: page
permalink: /team/
title: team
description: 
nav: true
---

{% for person in site.data.members %}

<!-- The paddingtop and margin-top edits allow anchors to link properly. -->
<div id = "{{person.name | replace: ' ', '-'}}" class="row" style="padding-top: 60px; margin-top: -60px; margin-left:0px">
    <div>
        <img class="pull-right" style="float: right; width: 43%; padding-left: 20px;" src="{{ person.image | prepend: '/assets/img/' | prepend: site.baseurl | prepend: site.url }}" alt="photo of {{person.name}}">
        <h4>{{person.name}}{% if person.degrees %}, {{person.degrees}} {% endif %}</h4> 
        {{person.position}} <br>
        {% if person.address %}
        <br>
          <i class="fa fa-map-marked-alt"></i> {{person.address}} <br>
        {% endif %}
        {% if person.phone %}
          <i class="fa fa-phone"></i> {{person.phone}} <br>
        {% endif %}
        <br>
        <i class="fa fa-envelope"></i> <em>{{person.email}}</em> <br>
        {% if person.twitter %}
          <i class="fab fa-twitter"></i> <a href= "http://twitter.com/{{person.twitter}}" target="_blank"> @{{person.twitter}} </a> <br>
        {% endif %}
        {% if person.website %}
          <i class="fa fa-globe"></i> <a href= "{{person.website}}" target="_blank">{{person.website}}</a> <br>
        {% endif %}
        {% if person.github %}
          <i class="fab fa-github"></i> <a href= "https://github.com/{{person.github}}" target="_blank"> {{person.github}} </a> <br>
        {% endif %}
        {% if person.scholar %}
          <i class="ai ai-google-scholar"></i> <a href= "http://scholar.google.com/citations?user={{person.scholar}}" target="_blank"> Scholar Citations </a> <br>
        {% endif %}
        {% if person.orcid %}
          <i class="ai ai-orcid"></i> <a href="http://{{person.orcid}}" target="_blank"> {{person.orcid}}</a> <br>
        {% endif %}
        <p class="text-justify">{{person.description | markdownify}}</p>
        {% if person.cv_page %}
        <a href="{{ person.cv_page | relative_url }}"> more...</a> <br>
        {% endif %}
    </div>
</div>
<hr>
{% endfor %}

{% if site.data.affiliates %}
  <h2>Student assistance / Bachelor & Master students</h2>
  <br>
  {% for person in site.data.affiliates %}
<div id = "{{person.name | replace: ' ', '-'}}" class="row" style="padding-top: 60px; margin-top: -60px; margin-left:0px">
    <div class = "col-md-12">
        <img class="pull-right" style="float: right; width: 43%; padding-left: 20px;" src="{{ person.image | prepend: '/assets/img/' | prepend: site.baseurl | prepend: site.url }}" alt="">
        <h4>{{person.name}}{% if person.degrees %}, {{person.degrees}} {% endif %}</h4> 
        {{person.position}} <br>
        <i class="fa fa-envelope"></i> <em>{{person.email}}</em> <br>
        {% if person.twitter %}
          <i class="fab fa-twitter"></i> <a href= "http://twitter.com/{{person.twitter}}" target="_blank"> @{{person.twitter}} </a> <br>
        {% endif %}
        {% if person.website %}
          <i class="fa fa-globe"></i> <a href= "{{person.website}}" target="_blank">{{person.website}}</a> <br>
        {% endif %}
        {% if person.github %}
          <i class="fab fa-github"></i> <a href= "https://github.com/{{person.github}}" target="_blank"> {{person.github}} </a> <br>
        {% endif %}
        {% if person.scholar %}
          <i class="ai ai-google-scholar"></i> <a href= "http://scholar.google.com/citations?user={{person.scholar}}" target="_blank"> Scholar Citations </a> <br>
        {% endif %}
        {% if person.orcid %}
          <i class="ai ai-orcid"></i> <a href="http://{{person.orcid}}" target="_blank"> {{person.orcid}}</a> <br>
        {% endif %}
        <p class="text-justify">{{person.description | markdownify}}</p>
        <!-- {% if person.cv_page %}
        <a href="{{ person.cv_page | relative_url }}"> more...</a> <br>
        {% endif %} -->
    </div>
</div>
<hr>
  {% endfor %}
{% endif %}

{% if site.data.students %}
  ## students
  {% for student in site.data.students %}

  <!-- The paddingtop and margin-top edits allow anchors to link properly. -->
  <div id = "{{student.name | replace: ' ', '-'}}" class="row" style="padding-top: 60px; margin-top: -60px; padding-bottom: 20px;">
    <strong>{{student.name}}{% if student.degrees %}, {{student.degrees}} {% endif %}</strong> <br>
    {{student.position}} <br>
    <i class="fa fa-envelope"></i> <em>{{student.email}}</em> <br>
    {% if student.description %}
    <div style="margin-left: 2.5em; padding-top: 8px; padding-bottom: 5px; ">{{student.description}}</div>
    {% else %}
    {% for paper in site.data.publications %}
    {% if paper.authors contains student.pubmed_name %}
    <div style="margin-left: 2.5em; padding-top: 8px; padding-bottom: 5px; ">{{paper.authors | remove: '**'}} <a href="/papers/index.html#{{paper.title}}">{{paper.title}}</a> {{paper.details}}</div>
    {% endif %}
    {% endfor %}
    {% endif %}
  </div>

  {% endfor %}
{% endif %}


{% if site.data.alumni %}
  <h2>Alumni</h2>
  <br>
  {% for person in site.data.alumni %}
<div id = "{{person.name | replace: ' ', '-'}}" class="row" style="padding-top: 60px; margin-top: -60px; margin-left:0px">
    <div class = "col-md-12">
        <img class="pull-right" style="float: right; width: 43%; padding-left: 20px;" src="{{ person.image | prepend: '/assets/img/' | prepend: site.baseurl | prepend: site.url }}" alt="">
        <h4>{{person.name}}{% if person.degrees %}, {{person.degrees}} {% endif %}</h4> 
        {{person.position}} <br>
        <i class="fa fa-envelope"></i> <em>{{person.email}}</em> <br>
        {% if person.twitter %}
          <i class="fab fa-twitter"></i> <a href= "http://twitter.com/{{person.twitter}}" target="_blank"> @{{person.twitter}} </a> <br>
        {% endif %}
        {% if person.website %}
          <i class="fa fa-globe"></i> <a href= "{{person.website}}" target="_blank">{{person.website}}</a> <br>
        {% endif %}
        {% if person.github %}
          <i class="fab fa-github"></i> <a href= "https://github.com/{{person.github}}" target="_blank"> {{person.github}} </a> <br>
        {% endif %}
        {% if person.scholar %}
          <i class="ai ai-google-scholar"></i> <a href= "http://scholar.google.com/citations?user={{person.scholar}}" target="_blank"> Scholar Citations </a> <br>
        {% endif %}
        {% if person.orcid %}
          <i class="ai ai-orcid"></i> <a href="http://{{person.orcid}}" target="_blank"> {{person.orcid}}</a> <br>
        {% endif %}
        <p class="text-justify">{{person.description | markdownify}}</p>
        <!-- {% if person.cv_page %}
        <a href="{{ person.cv_page | relative_url }}"> more...</a> <br>
        {% endif %} -->
    </div>
</div>
<hr>
  {% endfor %}
{% endif %}

{% if site.data.collaborators %}
  ---

  ## collaborators
  {% for collaborator in site.data.collaborators %}
  - <strong>{{collaborator.name}}{% if collaborator.degrees %}, {{collaborator.degrees}} {% endif %}</strong>  
    {{collaborator.position}}  
    {% if collaborator.website %} <i class="fa fa-globe"></i> <a href= "{{collaborator.website}}" target="_blank">{{collaborator.website}}</a>  {% endif %}
  {% endfor %}
{% endif %}