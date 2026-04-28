---
layout: layouts/base.njk
title: Home
permalink: /index.html
hero_text: "Expert mapping and communications for a greener and more sustainable future."
hero_bg_color: "#114B5F"
hero_svg_path: "M0,0 Q100,50 0,100 Z"
hero_image_1: "/assets/images/communications_nodes_graph_transparent.png"
hero_image_2: "/assets/images/mapstack_2.png"
hero_layout: "Diagonal Stagger"
hero_image_scale: "Large (max-w-lg)"
hero_image_spacing: "Standard (gap-12)"
---

<!-- Set up dynamic classes based on CMS selections -->
{% set layoutClass = "flex flex-col items-center justify-center" %}
{% set staggerClass1 = "" %}
{% set staggerClass2 = "" %}

{% if hero_layout == "Diagonal Stagger" %}
  {% set layoutClass = "grid grid-cols-2 items-center" %}
  {% set staggerClass1 = "transform lg:-translate-y-12" %}
  {% set staggerClass2 = "transform lg:translate-y-12" %}
{% elif hero_layout == "Side-by-Side (Desktop)" %}
  {% set layoutClass = "flex flex-col lg:flex-row items-center justify-center" %}
{% endif %}

{% set gapClass = "gap-12" %}
{% if hero_image_spacing == "Tight (gap-4)" %}{% set gapClass = "gap-4" %}
{% elif hero_image_spacing == "Loose (gap-20)" %}{% set gapClass = "gap-20" %}{% endif %}

{% set scaleClass = "max-w-md" %}
{% if hero_image_scale == "Small (max-w-sm)" %}{% set scaleClass = "max-w-sm" %}
{% elif hero_image_scale == "Large (max-w-lg)" %}{% set scaleClass = "max-w-lg" %}
{% elif hero_image_scale == "Full Width (w-full)" %}{% set scaleClass = "w-full" %}{% endif %}

<!-- Hero Section -->
<section class="relative w-full overflow-hidden flex flex-col lg:flex-row min-h-[80vh] bg-white">
  
  <!-- Dynamic Background Color & SVG Curve (Desktop) -->
  <div class="absolute inset-0 w-full lg:w-1/2 h-full z-0" style="background-color: {{ hero_bg_color }};">
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

    <!-- Right Column: Dynamic Images -->
    <div class="w-full lg:w-1/2 {{ layoutClass }} {{ gapClass }} relative z-10">
      {% if hero_image_1 %}
        <img src="{{ hero_image_1 }}" alt="Hero Image 1" class="w-full {{ scaleClass }} h-auto {{ staggerClass1 }}">
      {% endif %}
      
      {% if hero_image_2 %}
        <img src="{{ hero_image_2 }}" alt="Hero Image 2" class="w-full {{ scaleClass }} h-auto {{ staggerClass2 }}">
      {% endif %}
    </div>

  </div>
</section>
