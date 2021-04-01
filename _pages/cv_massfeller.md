---
layout: page
permalink: /cv_massfeller/
title: Anna Massfeller
nav: false
---

<!-- The paddingtop and margin-top edits allow anchors to link properly. -->
{% for person in site.data.members %}
{% if person.name == "Anna Massfeller" %}
<div id = "{{person.name | replace: ' ', '-'}}" class="row" style="padding-top: 60px; margin-top: -60px; margin-left:0px">
    <div>
        <img class="pull-right" style="float: right; width: 43%; padding-left: 20px;" src="{{ person.image | prepend: '/assets/img/' | prepend: site.baseurl | prepend: site.url }}" alt="photo of {{person.name}}">
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
    </div>
</div>
{% endif %}
{% endfor %}

<div class="cv">
	{% for entry in site.data.cv_massfeller %}
		<div class="card mt-3 p-3">
			<h3 class="card-title">{{ entry.title }}</h3>
			<div>
			{% if entry.type == "list" %}
				<ul class="card-text font-weight-light list-group list-group-flush">
				{% for content in entry.contents %}
					<li class="list-group-item">{{ content }}</li>
				{% endfor %}
				</ul>
			{% elsif entry.type == "map" %}
				<table class="table table-sm table-borderless">
					{% for content in entry.contents %}
						<tr>
							<td class="p-0 pr-2 font-weight-bold text-right"><b>{{ content.name }}</b></td>
							<td class="p-0 pl-2 font-weight-light text-left">{{ content.value }}</td>
						</tr>
					{% endfor %}
				</table>
			{% elsif entry.type == "nested_list" %}
				<ul class="card-text font-weight-light list-group list-group-flush">
				{% for content in entry.contents %}
					<li class="list-group-item">
					<h5 class="font-italic">{{ content.title }}</h5>
					{% if content.items %}
						<ul class="subitems">
								{% for subitem in content.items %}
									<li><span class="subitem">{{ subitem }}</span></li>
								{% endfor %}
								</ul>
							{% endif %}
					</li>
				{% endfor %}
				</ul>
			{% elsif entry.type == "table" %}
				<ul class="card-text font-weight-light list-group list-group-flush">
				{% for content in entry.contents %}
					<li class="list-group-item">
						<div class="row">
							{% if content.year %}
								<div class="col-xs-2 cl-sm-2 col-md-auto text-left" style="width: 90px;">
									<span class="badge font-weight-bold light-green darken-1 text-uppercase align-middle" style="width: 90px;">
										{{ content.year }}
									</span>
								</div>
							{% endif %}
							<div class="col-xs-10 cl-sm-10 col-md mt-2 mt-md-0">
								{% if content.title %}
								<h6 class="title font-weight-bold ml-1 ml-md-4">{{content.title}}</h6>
								{% endif %}
								{% if content.description %}
									<ul class="items">
										{% for item in content.description %}
										    <li>
												{% if item.contents %}
													<span class="item-title">{{ item.title }}</span>
													<ul class="subitems">
													{% for subitem in item.contents %}
														<li><span class="subitem">{{ subitem }}</span></li>
													{% endfor %}
													</ul>
												{% else %}
													<span class="item">{{ item }}</span>
												{% endif %}
											</li>
										{% endfor %}
									</ul>
								{% endif %}
								{% if content.items %}
									<ul class="items">
										{% for item in content.items %}
											<li>
												{% if item.contents %}
													<span class="item-title">{{ item.title }}</span>
													<ul class="subitems">
													{% for subitem in item.contents %}
														<li><span class="subitem">{{ subitem }}</span></li>
													{% endfor %}
													</ul>
												{% else %}
													<span class="item">{{ item }}</span>
												{% endif %}
											</li>
										{% endfor %}
									</ul>
								{% endif %}
							</div>
						</div>
					</li>
				{% endfor %}
				</ul>
            {% elsif entry.type == "table-no-bullets" %}
                <ul class="card-text font-weight-light list-group list-group-flush">
                {% for content in entry.contents %}
                    <li class="list-group-item">
                        <div class="row">
                            {% if content.year %}
                                <div class="col-xs-2 cl-sm-2 col-md-auto text-left" style="width: 90px;">
                                    <span class="badge font-weight-bold light-green darken-1 text-uppercase align-middle" style="width: 90px;">
                                        {{ content.year }}
                                    </span>
                                </div>
                            {% endif %}
                            <div class="col-xs-10 cl-sm-10 col-md mt-2 mt-md-0">
                                {% if content.title %}
                                <h6 class="title font-weight-bold ml-1 ml-md-4">{{content.title}}</h6>
                                {% endif %}
                                {% if content.description %}
                                    <ul class="items">
                                        {% for item in content.description %}
                                            <li style="list-style-type: none;">
                                                {% if item.contents %}
                                                    <span class="item-title">{{ item.title }}</span>
                                                    <ul class="subitems">
                                                    {% for subitem in item.contents %}
                                                        <li><span class="subitem">{{ subitem }}</span></li>
                                                    {% endfor %}
                                                    </ul>
                                                {% else %}
                                                    <span class="item">{{ item }}</span>
                                                {% endif %}
                                            </li>
                                        {% endfor %}
                                    </ul>
                                {% endif %}
                                {% if content.items %}
                                    <ul class="items">
                                        {% for item in content.items %}
                                            <li>
                                                {% if item.contents %}
                                                    <span class="item-title">{{ item.title }}</span>
                                                    <ul class="subitems">
                                                    {% for subitem in item.contents %}
                                                        <li><span class="subitem">{{ subitem }}</span></li>
                                                    {% endfor %}
                                                    </ul>
                                                {% else %}
                                                    <span class="item">{{ item }}</span>
                                                {% endif %}
                                            </li>
                                        {% endfor %}
                                    </ul>
                                {% endif %}
                            </div>
                        </div>
                    </li>
                {% endfor %}
                </ul>
            {% endif %}
            {% if entry.note %}
                <span class="card-text font-weight-light">{{ entry.note }}</span>
            {% endif %}
			</div>
		</div>
	{% endfor %}
</div>