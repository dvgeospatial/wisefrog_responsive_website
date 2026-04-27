---
layout: layouts/page.njk
title: Our Services
---

*Here is a list of the mapping and communication services we provide.*

<div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6 mt-12 not-prose">
  {% for service in collections.allServices %}
    <div class="bg-white rounded-lg shadow-md overflow-hidden border border-gray-200 hover:shadow-lg transition-shadow">
      <div class="p-6">
        <h3 class="text-xl font-bold text-blue-900 mb-3">{{ service.data.title }}</h3>
        <p class="text-gray-600 mb-4">{{ service.templateContent | striptags | truncate(150) }}</p>
      </div>
    </div>
  {% else %}
    <p>No services found in the system yet.</p>
  {% endfor %}
</div>
