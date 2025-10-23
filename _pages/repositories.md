---
layout: page
permalink: /repositories/
title: Repositories
description: Overview of public repositories.
nav: false
nav_order: 7

---

## GitHub users

{% if site.data.repositories.github_users %}
<div class="repositories d-flex flex-wrap flex-md-row flex-column justify-content-between align-items-center">
  {% for user in site.data.repositories.github_users %}
    {% include repository/repo_user.html username=user %}
  {% endfor %}
</div>
{% endif %}

---

{% if site.repo_trophies.enabled %}
  {% for user in site.data.repositories.github_users %}
    {% if site.data.repositories.github_users.size > 1 %}
      <h4>{{ user }}</h4>
    {% endif %}
    <div class="repositories d-flex flex-wrap flex-md-row flex-column justify-content-between align-items-center">
      {% include repository/repo_trophies.html username=user %}
    </div>
  {% endfor %}
{% endif %}


## Repositories

{% if site.data.repositories.github_repos %}
<div class="repositories d-flex flex-wrap flex-md-row flex-column justify-content-between align-items-center">
  {% for repo in site.data.repositories.github_repos %}
    {% include repository/repo.html repository=repo %}
  {% endfor %}
</div>
{% endif %}

<!-- Show the HAO gitlab page -->
<div class="repo p-2 text-center">
  <a href="https://gitlab.com/issahanou/hao">
    <img class="repo-img-dark w-100" alt="issahanou/HAO" src="../assets/img/HAO_img.png">
  </a>
</div>

{% if site.data.repositories.github_organizations %}
  <div class="repositories d-flex flex-wrap flex-md-row flex-column justify-content-between align-items-center">
  {% for org in site.data.repositories.github_organizations %}
    <a style="font-size: 1.5rem;" href="{{ org.link }}">{{ org.name }}</a>
    <div class="repositories d-flex flex-wrap flex-md-row flex-column justify-content-between align-items-center">
      {% for repo in org.repos %}
        {% include repository/repo_org.html repository=repo organization=org.name%}
      {% endfor %}
    </div>
  {% endfor %}
  </div>
{% endif %}

