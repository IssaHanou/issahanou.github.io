---
layout: page
title: News
permalink: /news_overview/
description: An overview of news items over the years.
nav: true
nav_order: 1
---

<div class="news_overview">
    {% for year in site.news_overview %}
        <a class="abstract btn btn-sm z-depth-0" href="{{ year.url | relative_url }}">{{ year.year }}</a>
        {% endfor %}
</div>

<br>

<h3>All news</h3>
<div class="news_per_year">
    {%- assign news = site.news | reverse -%}
    <div class="table-responsive">
        <table class="table table-sm table-borderless">
        {% for item in news %}
        <tr>
            <th scope="row">{{ item.date | date: "%b %-d, %Y" }}</th>
            <td>
            {% if item.inline -%}
                {{ item.content | remove: '<p>' | remove: '</p>' | emojify }}
            {%- else -%}
                <a class="news-title" href="{{ item.url | relative_url }}">{{ item.title }}</a>
            {%- endif %}
            </td>
        </tr>
        {%- endfor %}
        </table>
    </div>
</div>
