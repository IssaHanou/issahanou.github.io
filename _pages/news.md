---
layout: page
title: News
permalink: /all_news
description: An overview of my news items over the years.
nav: false
nav_order: 0
---

<!-- Cannot sort based on clicked year in real-time using Jekyll -->

<div class="news_per_year">
    {%- assign news = site.news | reverse -%}
    {%- assign years = site.news | group_by: "year" -%}
    {% for item in years %}
        <a class="news-year-{{item.name}}" href="/all_news/{{item.name }}"> {{ item.name }}</a>
        {%- assign curNews = item.items -%}
    {% endfor %}
    <div class="table-responsive">
        <table class="table table-sm table-borderless">
        {% for item in curNews %}
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

<script>
    // Define the getYears function
    function getYears(news) {
        const years = [];
        news.forEach(item => {
            const year = item.date.substring(0, 4); // Extract the year part of the date string
            if (!years.includes(year)) {
                years.push(year); // Add the year to the list if it's not already included
            }
        });
        console.log(years);
        return years;
    }

    function filterNews(year) {
        var newsItems = document.querySelectorAll('.news-item');
        newsItems.forEach(function(item) {
            var itemYear = item.getAttribute('data-year');
            if (itemYear === year || year === 'all') {
                item.style.display = 'block';
            } else {
                item.style.display = 'none';
            }
        });
    }
</script>
