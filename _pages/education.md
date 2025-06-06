---
layout: page
permalink: /education/
title: Education
description: Students I supervised and other teaching activities.
nav: true
nav_order: 3
pdf1: 'ai-planning-slides.pdf'
pdf2: 'ai-planning-notes.pdf'
---

I give a lecture on AI planning in the course 'Probabilistic AI & Reasoning' at TU Delft for the Artificial Intelligence master. I first gave this lecture in September 2024 and will do the same in 2025. 
You can find <a href="{{ page.pdf1 | prepend: 'assets/pdf/' | relative_url}}" target="_blank">the slides here</a> and <a href="{{ page.pdf2 | prepend: 'assets/pdf/' | relative_url}}" target="_blank">the lecture notes here</a>.

<br>
## Thesis supervision



<div class="students">
    <p>I am/was involved in several theses as the daily supervisor.</p>    
    {%- assign theses = site.data.supervision | group_by: "type" -%}
    {% for type in theses %}
        <div class="theses">
            <h4><b>{{ type.name }}</b></h4>
            {%- assign thesesTypes = type.items | sort: "start" | reverse -%}
            {% for thesis in thesesTypes %}
                <div class="thesis" id="{{ thesis.id }}">
                    {% if type.name == "MSc theses" %}
                        {% if thesis.post_name %}
                            <h5><a href="{{ thesis.link }}" class="{{ thesis.status }}" target="_blank">{{ thesis.topic }}</a></h5>
                            <p> {{ thesis.name }} ({{ thesis.year }})</p>
                        {% else %}
                            <h5><a href="{{ thesis.link }}" class="{{ thesis.status }}" target="_blank">{{ thesis.topic }} ({{ thesis.year }})</a></h5>
                        {% endif %}
                    {% else %}
                        <h5>{{ thesis.topic }} ({{ thesis.year }})</h5>
                    {% endif %}
                    <p> {{ thesis.abstract }} </p>
                    <div class="keywords">
                        {% for key in thesis.keywords %}
                            <div class="abstract btn btn-sm z-depth-0 keyword">
                                {{ key }}
                            </div>
                        {% endfor %}
                    </div>
                    {% if type.name == "BSc theses" %}
                        <ul>
                            {% for project in thesis.sub-projects %}
                                <li><a href="{{ project.link }}" target="_blank">{{ project.title }}</a></li>
                            {% endfor %}
                        </ul>
                    {% endif %}
                </div>  
            {% endfor %}
            <br>
        </div>
    {% endfor %}
</div>
