---
title: Home
hero_text: Expert mapping and communications for a greener and more sustainable future.
hero_bg_color: "#114B5F"
hero_svg_path: M0,0 L85,0 Q3.950000000000003,47 100,100 L0,100 Z
hero_image_1: /assets/images/communications_nodes_graph_transparent.png
hero_image_2: /assets/images/mapstack_2.png
hero_image_scale: Full Width (w-full)
layout: layouts/base.njk
permalink: /index.html
hero_layout: Stacked Centered
hero_image_spacing: Tight (gap-4)
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
{% set overlapClass = "" %}
{% if hero_image_spacing == "Overlap (-mt-12)" %}
  {% set gapClass = "gap-0" %}
  {% set overlapClass = "-mt-12 lg:-mt-24 z-0 relative" %}
{% elif hero_image_spacing == "Flush (gap-0)" %}
  {% set gapClass = "gap-0" %}
{% elif hero_image_spacing == "Tight (gap-4)" %}
  {% set gapClass = "gap-4" %}
{% elif hero_image_spacing == "Loose (gap-20)" %}
  {% set gapClass = "gap-20" %}
{% endif %}

{% set scaleClass = "max-w-md" %}
{% if hero_image_scale == "Small (max-w-sm)" %}{% set scaleClass = "max-w-sm" %}
{% elif hero_image_scale == "Large (max-w-lg)" %}{% set scaleClass = "max-w-lg" %}
{% elif hero_image_scale == "Full Width (w-full)" %}{% set scaleClass = "w-full" %}{% endif %}

<!-- Hero Section -->
<section class="relative w-full overflow-hidden flex flex-col lg:flex-row  bg-white">
  
  <!-- Dynamic Background Color & SVG Curve (Desktop) -->
  <div class="absolute inset-0 w-full lg:w-1/2 h-full z-0" style="background-color: {{ hero_bg_color }};">
    <svg class="hidden lg:block absolute top-0 left-full h-full w-[200px] xl:w-[300px]" preserveAspectRatio="none" viewBox="0 0 100 100" fill="currentColor" style="color: {{ hero_bg_color }};">
      <path d="{{ hero_svg_path }}" />
    </svg>
  </div>

  <!-- Content Container -->
  <div class="relative z-10 w-full max-w-screen-2xl mx-auto px-4 sm:px-6 lg:px-8 py-8 lg:py-8 flex flex-col lg:flex-row items-center justify-between">
    
    <!-- Left Column: Text Content -->
    <div class="w-full lg:-mt-24 lg:w-[45%] text-white text-center lg:text-left mb-8 lg:mb-0">
      <h1 class="text-4xl md:text-3xl lg:text-4xl font-bold leading-tight">
        {{ hero_text }}
      </h1>
    </div>

    <!-- Right Column: Dynamic Images -->
    <div class="w-full lg:w-1/2 {{ layoutClass }} {{ gapClass }} relative z-10">
      {% if hero_image_1 == "/assets/images/communications_nodes_graph_transparent.png" %}
      <div class="w-full {{ scaleClass }} h-auto {{ staggerClass1 }} relative z-20 hover:cursor-grab active:cursor-grabbing">
        {% include "components/d3-network.njk" %}
      </div>
    {% elif hero_image_1 %}
      <img src="{{ hero_image_1 }}" alt="Hero Image 1" class="w-full {{ scaleClass }} h-auto {{ staggerClass1 }} relative z-20">
    {% endif %}
      
      {% if hero_image_2 %}
        <img src="{{ hero_image_2 }}" alt="Hero Image 2" class="w-full {{ scaleClass }} h-auto {{ staggerClass2 }} {{ overlapClass }}">
      {% endif %}
    </div>

  </div>
</section>
