---
layout: page
permalink: /services/
title: services
description: Academic Services
nav: true
nav_order: 5
---


<!-- pages/services.md -->
<div class="services">
{% if site.services != blank -%} 
<div class="table-responsive">
    <table class="table table-sm table-borderless">
    {%- assign services = site.services | reverse -%} 
    {% for item in services %} 
    <tr>
        <th scope="row">{{ item.date | date: "%b %-d, %Y" }}</th>
        <td>
        {% if item.inline -%} 
            {{ item.content | remove: '<p>' | remove: '</p>' | emojify }}
        {%- else -%} 
            <a class="services-title" href="{{ item.url | relative_url }}">{{ item.title }}</a>
        {%- endif %} 
        </td>
        <td>
        {% if item.place -%} 
            <span class="services-place">{{ item.place }}</span>
        {%- endif %}
        </td>
    </tr>
    {%- endfor %} 
    </table>
</div>
{%- else -%} 
<p>No services so far...</p>
{%- endif %} 
</div>