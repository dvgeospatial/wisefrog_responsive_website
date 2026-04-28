---
title: Home
hero_text: Expert mapping and communications for a greener and more sustainable future.
hero_image_1: /assets/images/communications_nodes_graph_transparent.png
hero_image_2: /assets/images/mapstack_2.png
hero_bg_color: "#114B5F"
hero_svg_path: M0,0 L100,0 Q-40,50 100,100 L0,100 Z
layout: layouts/base.njk
permalink: /index.html
---

<!-- Hero Section -->
<section class="relative w-full overflow-hidden flex flex-col lg:flex-row min-h-[80vh] bg-white">
  
  <!-- Dynamic Background Color & SVG Curve (Desktop) -->
  <div class="absolute inset-0 w-full lg:w-1/2 h-full z-0" style="background-color: {{ hero_bg_color }};">
    <!-- The curve perfectly attached to the right edge of the background block -->
    <!-- The d="..." attribute is now completely controlled by the CMS -->
    <svg class="hidden lg:block absolute top-0 left-full h-full w-[200px] xl:w-[300px]" preserveAspectRatio="none" viewBox="0 0 100 100" fill="currentColor" style="color: {{ hero_bg_color }};">
      <path d="{{ hero_svg_path }}" />
    </svg>
  </div>

  <!-- Content Container -->
  <div class="relative z-10 w-full max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-16 lg:py-24 flex flex-col lg:flex-row items-center justify-between">
    
    <!-- Left Column: Text Content -->
    <div class="w-full lg:w-[45%] text-white text-center lg:text-left mb-16 lg:mb-0">
      <h1 class="text-4xl md:text-5xl lg:text-6xl font-bold leading-tight">
        {{ hero_text }}
      </h1>
    </div>

    <!-- Right Column: Images -->
    <div class="w-full lg:w-1/2 flex flex-col items-center justify-center gap-12 relative z-10">
      {% if hero_image_1 %}
        <img src="{{ hero_image_1 }}" alt="Network Diagram" class="w-full max-w-md h-auto">
      {% endif %}
      
      {% if hero_image_2 %}
        <img src="{{ hero_image_2 }}" alt="Layered Map" class="w-full max-w-md h-auto">
      {% endif %}
    </div>

  </div>
</section>
