---
layout: layouts/page.njk
title: Our Services
---

*SUPER TEST: Here is a list of the mapping and communication services we provide.*

<div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-6 mt-12 not-prose">
  {% for service in collections.services %}
    <div class="bg-white rounded-lg shadow-md overflow-hidden border border-gray-200 hover:shadow-lg transition-shadow">
      <div class="p-6">
        <h3 class="text-xl font-bold text-blue-900 mb-3">{{ service.data.title }}</h3>
        <p class="text-gray-600 mb-4">{{ service.content | striptags | truncate(150) }}</p>
      </div>
    </div>
  {% else %}
    <div class="bg-yellow-100 p-6 rounded-lg text-yellow-800">
      The loop works, but no services with the correct tags were found!
    </div>
  {% endfor %}
</div>
