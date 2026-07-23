---
layout: page
permalink: /repositories/
title: repositories
description: A few of my GitHub projects (many are still in development!)
nav: true
nav_order: 4
---

{% if site.data.repositories.github_users %}

## GitHub

<div class="row row-cols-1 row-cols-md-2 g-4">
  {% for user_entry in site.data.repositories.github_users %}
    {% assign github_user = user_entry.username | default: user_entry %}
    {% assign github_name = user_entry.name | default: github_user %}
    {% assign github_blurb = user_entry.blurb | default: "Code, pipelines, and research tooling." %}
    <div class="col">
      <div class="card hoverable h-100">
        <div class="card-body">
          <h3 class="card-title text-lowercase">
            <a href="https://github.com/{{ github_user }}" target="_blank" rel="noopener noreferrer">{{ github_name }}</a>
          </h3>
          <p class="card-text">{{ github_blurb }}</p>
          <p class="post-meta">
            <a href="https://github.com/{{ github_user }}" target="_blank" rel="noopener noreferrer">github.com/{{ github_user }}</a>
          </p>
        </div>
      </div>
    </div>
  {% endfor %}
</div>
{% endif %}

{% if site.data.repositories.github_repos %}
{% if site.data.repositories.github_users %}

---

{% endif %}

## GitHub Repositories

<div class="row row-cols-1 row-cols-md-2 g-4">
  {% for repo_entry in site.data.repositories.github_repos %}
    {% assign repo_path = repo_entry.repo | default: repo_entry %}
    {% assign repo_name = repo_entry.name | default: repo_path | split: "/" | last %}
    {% assign repo_description = repo_entry.description | default: "Repository link." %}
    {% assign repo_url = repo_entry.url | default: "https://github.com/" | append: repo_path %}
    <div class="col">
      <div class="card hoverable h-100">
        <div class="card-body">
          <h3 class="card-title text-lowercase">
            <a href="{{ repo_url }}" target="_blank" rel="noopener noreferrer">{{ repo_name }}</a>
          </h3>
          <p class="card-text">{{ repo_description }}</p>
          <p class="post-meta">
            <a href="{{ repo_url }}" target="_blank" rel="noopener noreferrer">{{ repo_path }}</a>
          </p>
        </div>
      </div>
    </div>
  {% endfor %}
</div>
{% endif %}
