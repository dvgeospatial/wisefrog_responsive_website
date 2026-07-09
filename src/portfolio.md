---
layout: layouts/page.njk
title: Our Portfolio
---

We use digital mapping and communication tools to support nature recovery and sustainable development across Norfolk, Suffolk, and beyond.

Below are selected projects. Each page showcases a specific aspect of our work, with maps, images, and interactive elements where appropriate.

<div class="grid grid-cols-1 md:grid-cols-2 gap-6 mt-10 not-prose">
  {% for project in collections.allPortfolioEntries %}
    <article class="bg-white rounded-lg shadow-md overflow-hidden border border-gray-200 hover:shadow-lg transition-shadow">
      <a href="{{ project.url }}" class="block h-full">
        <div class="p-6 space-y-4">
          <h2 class="text-xl font-bold text-blue-900">
            {{ project.data.title }}
          </h2>

          {% if project.data.summary %}
            <p class="text-gray-600">
              {{ project.data.summary }}
            </p>
          {% else %}
            <p class="text-gray-600">
              {{ project.content | striptags | truncate(150) }}
            </p>
          {% endif %}

          {% if project.data.teaser_image %}
            <figure class="mt-4">
              <img
                src="{{ project.data.teaser_image }}"
                alt="{{ project.data.title }}"
                class="w-full h-40 object-cover rounded-lg bg-gray-100"
              >
            </figure>
          {% endif %}
        </div>
      </a>
    </article>
  {% else %}
    <div class="bg-gray-100 p-6 rounded-lg text-gray-600 text-center md:col-span-2">
      No portfolio entries have been added yet. Log into the CMS to create your first portfolio page.
    </div>
  {% endfor %}
</div>
