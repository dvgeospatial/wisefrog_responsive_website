---
title: Home
hero_text: Expert mapping and communications for a greener and more sustainable future.
hero_bg_style: Solid Color 1
hero_bg_color: "#114B5F"
hero_bg_color_2: "#31c2da"
hero_svg_path: M0,0 L48,0 Q-47.08,46 46,100 L0,100 Z
hero_image_1: /assets/images/communications_nodes_graph_transparent.png
hero_image_2: /assets/images/mapstack_2.png
hero_image_scale: Large (max-w-lg)
carousel_section:
  items:
    - image: /assets/images/mapstack_2.png
      text: stack of maps
      url: https://tourmaline-pudding-0fce6c.netlify.app/services/
    - image: /assets/images/communications_nodes_graph_transparent.png
      text: network
      url: https://tourmaline-pudding-0fce6c.netlify.app/services/
    - image: /assets/images/screenshot_2026-04-03_14-30-20-portrait.webp
      text: Norwich city
      url: https://tourmaline-pudding-0fce6c.netlify.app/services/
  global_shadow_intensity: Light
  heading: Smart mapping that delivers insight, informs decisions, and promotes
    collaboration
layout: layouts/base.njk
permalink: /index.html
hero_layout: Stacked Centered
hero_image_spacing: Flush (gap-0)
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
  {% set overlapClass = "-mt-12 lg:-mt-12 2xl:-mt-0 2xl:-mt-0 z-0 relative" %}
{% elif hero_image_spacing == "Flush (gap-0)" %}
  {% set gapClass = "gap-0" %}
{% elif hero_image_spacing == "Tight (gap-4)" %}
  {% set gapClass = "gap-4" %}
{% elif hero_image_spacing == "Loose (gap-20)" %}
  {% set gapClass = "gap-20" %}
{% endif %}

{% set scaleClass = "max-w-xs md:max-w-sm lg:max-w-xs 2xl:max-w-lg" %}
{% if hero_image_scale == "Small (max-w-sm)" %}{% set scaleClass = "max-w-xs md:max-w-xs lg:max-w-xs 2xl:max-w-md" %}
{% elif hero_image_scale == "Large (max-w-lg)" %}{% set scaleClass = "max-w-sm md:max-w-md lg:max-w-sm 2xl:max-w-xl" %}
{% elif hero_image_scale == "Full Width (w-full)" %}{% set scaleClass = "w-full" %}
{% endif %}

<!-- Hero Section -->
<section class="relative w-full overflow-hidden flex flex-col lg:flex-row  bg-white  2xl:min-h-[calc(100vh-64px)]">
  
  <!-- Dynamic Background Color & SVG Curve (Desktop) -->
  <!-- 2-Color Dynamic Hero Background -->
  {% set heroStyle = "background-color: " ~ hero_bg_color ~ ";" %}
  {% if hero_bg_style == "Pure White (No Gradient)" %}
    {% set heroStyle = "background-color: #ffffff;" %}
  {% elif hero_bg_style == "Subtle Gradient (Color 1 to Color 2)" %}
    {% set endColor = hero_bg_color_2 | default("#ffffff") %}
    {% set heroStyle = "background: linear-gradient(135deg, " ~ hero_bg_color ~ " 0%, " ~ endColor ~ " 100%);" %}
  {% endif %}
  <div class="absolute inset-0 w-full lg:w-1/2 h-full z-0" style="{{ heroStyle }}">
    <svg class="hidden lg:block absolute top-0 left-full h-full w-[200px] xl:w-[300px]" preserveAspectRatio="none" viewBox="0 0 100 100" fill="currentColor" style="color: {{ hero_bg_color }};">
      <path d="{{ hero_svg_path }}" />
    </svg>
  </div>

  <!-- Content Container -->
  <div class="relative z-10 w-full max-w-screen-2xl mx-auto px-4 sm:px-6 lg:px-8 py-4 lg:py-2 2xl:py-12 flex flex-col lg:flex-row items-center justify-between">
    
    <!-- Left Column: Text Content -->
    <div class="w-full lg:-mt-12 2xl:-mt-0 2xl:-mt-0 lg:w-[45%] text-white text-center lg:text-left mb-16 lg:mb-0">
      <h1 class="text-2xl md:text-3xl lg:text-4xl 2xl:text-6xl 2xl:leading-snug md:leading-tight font-bold leading-snug md:leading-tight">
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

<!-- Dynamic Card Carousel Section -->
<section class="w-full bg-white py-16 lg:py-24 overflow-hidden border-t border-gray-100">
  <div class="max-w-screen-2xl mx-auto px-4 sm:px-6 lg:px-8">
    
    <!-- Carousel Heading -->
    <div class="max-w-5xl mb-12">
      <h2 class="text-2xl md:text-3xl lg:text-4xl font-bold text-gray-900 leading-snug">
        {{ carousel_section.heading | default("Smart mapping that delivers practical insight, informs decisions, promotes collaboration, and helps deliver effective nature recovery measures on the ground") }}
      </h2>
    </div>

    <!-- The Swipeable Container -->
    <!-- Native horizontal scrolling, snapping, and hidden scrollbars for app-like swiping -->
    <div class="flex overflow-x-auto snap-x snap-mandatory gap-6 pb-8 -mx-4 px-4 sm:mx-0 sm:px-0 hide-scrollbar" style="scrollbar-width: none; -ms-overflow-style: none;">
      
      <!-- Loop through the CMS items -->
      {% if carousel_section and carousel_section.items %}
        {% for item in carousel_section.items %}
        <!-- Individual Card (Portrait Aspect Ratio) -->
        <a href="{{ item.url }}" class="group relative flex-none w-72 md:w-80 lg:w-96 aspect-[3/4] snap-start rounded-2xl overflow-hidden shadow-lg transition-transform duration-300 hover:-translate-y-2 hover:shadow-2xl bg-gray-200">
          
          <!-- Background Image -->
          <img src="{{ item.image }}" alt="{{ item.text }}" class="absolute inset-0 w-full h-full object-cover transition-transform duration-500 group-hover:scale-110">
          
          <!-- Dark Gradient Overlay for text readability -->
          <!-- Global Shadow Overlay based on CMS selection -->
          {% set shadowClass = "from-black/60 via-black/20" %}
          {% if carousel_section.global_shadow_intensity == "Heavy" %}
            {% set shadowClass = "from-black/90 via-black/40" %}
          {% elif carousel_section.global_shadow_intensity == "Light" %}
            {% set shadowClass = "from-black/30 via-transparent" %}
          {% elif carousel_section.global_shadow_intensity == "None" %}
            {% set shadowClass = "from-transparent via-transparent" %}
          {% endif %}
          <div class="absolute inset-0 bg-gradient-to-t {{ shadowClass }} to-transparent pointer-events-none"></div>
          
          <!-- Overlay Text -->
          <div class="absolute bottom-0 left-0 right-0 p-6">
            <h3 class="text-white text-xl md:text-2xl font-bold leading-tight">{{ item.text }}</h3>
          </div>
        </a>
        {% endfor %}
      {% else %}
        <!-- Fallback if CMS is empty -->
        <div class="text-gray-500 italic py-12">Log into the CMS to add your first Carousel Item!</div>
      {% endif %}

    </div>
  </div>
</section>

<style>
/* Hide scrollbar for Chrome, Safari and Opera */
.hide-scrollbar::-webkit-scrollbar {
  display: none;
}
</style>

