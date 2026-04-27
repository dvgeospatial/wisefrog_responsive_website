---
layout: layouts/page.njk
title: Our Services
---

*Here is a complete list of the mapping and communication services we provide.*

<div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6 mt-12 not-prose">
  {% for service in collections.allServices %}
    <div class="bg-white rounded-lg shadow-md overflow-hidden border border-gray-200 hover:shadow-lg transition-shadow">
      <div class="p-6">
        <h3 class="text-xl font-bold text-blue-900 mb-3">{{ service.data.title }}</h3>
        <p class="text-gray-600 mb-4">{{ service.content | striptags | truncate(150) }}</p>
      </div>
    </div>
  {% else %}
    <div class="bg-gray-100 p-6 rounded-lg text-gray-600 text-center">
      No services have been added yet. Log into the CMS to add your first service!
    </div>
  {% endfor %}
</div>
