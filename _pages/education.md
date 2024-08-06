---
layout: page
permalink: /education/
title: Education
description: Students I supervised and other teaching activities.
nav: true
nav_order: 5
---

## Lectures

In September 2024, I will give the first lesson on AI planning at TU Delft, in the new course 'Probabilistic AI & Reasoning'. You can find the slides <a href="assets/pdf/ai-planning-slides.pdf" target="_blank">here</a>.

## Thesis supervision



<div class="students">
    <p>I am/was involved in several theses as the daily supervisor.</p>    
    {%- assign theses = site.data.supervision | group_by: "type" -%}
    {% for type in theses %}
        <div class="theses">
            <h4><b>{{ type.name }}</b></h4>
            {%- assign thesesTypes = type.items | sort: "year" | reverse -%}
            {% for thesis in thesesTypes %}
                <div class="thesis">
                    {% if type.name == "MSc thesis" %}
                        <h5><a href="{{ thesis.link }}" class="{{ thesis.status }}" target="_blank">{{ thesis.topic }}</a></h5>
                        <p> {{ thesis.name }} ({{ thesis.year }})</p>
                        <p> {{ thesis.abstract }} </p>
                    {% else %}
                        <h5>{{ thesis.topic }} ({{ thesis.year }})</h5>
                        <p> {{ thesis.abstract }} </p>
                    {% endif %}
                    <div class="keywords">
                        {% for key in thesis.keywords %}
                            <div class="abstract btn btn-sm z-depth-0 keyword">
                                {{ key }}
                            </div>
                        {% endfor %}
                    </div>
                    {% if type.name == "BSc thesis" %}
                        <ul>
                            {% for project in thesis.subprojects %}
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
