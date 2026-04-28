---
title: Home
hero_text: Expert mapping and communications for a greener and more sustainable future.
hero_image_1: /assets/images/communications_nodes_graph_transparent.png
hero_image_2: /assets/images/mapstack_2.png
hero_bg_color: "#114B5F"
hero_svg_path: "cat << 'EOF' > output/curve-tool-v6.html <!DOCTYPE html> <html
  lang=\"en\"> <head>     <meta charset=\"UTF-8\">     <meta name=\"viewport\"
  content=\"width=device-width, initial-scale=1.0\">     <title>SVG Arc
  Authoring Tool V6</title>     <script
  src=\"https://cdn.tailwindcss.com\"></script>     <style>         body {
  font-family: system-ui, -apple-system, sans-serif; background: #f3f4f6;
  }     </style> </head> <body class=\"p-8\">     <div class=\"max-w-6xl mx-auto
  bg-white rounded-xl shadow-lg p-8 grid grid-cols-1 md:grid-cols-2
  gap-8\">                  <!-- Left: Controls & Code
  -->         <div>             <h1 class=\"text-2xl font-bold mb-6\">Hero
  Banner Arc Generator (Full Height)</h1>                          <div
  class=\"space-y-6 mb-8\">                 <div>                     <label
  class=\"block text-sm font-medium text-gray-700 mb-2\">Arc Depth (Middle Point
  X)</label>                     <input type=\"range\" id=\"mid_x\" min=\"0\"
  max=\"100\" value=\"50\" class=\"w-full\"
  oninput=\"updatePath()\">                     <p class=\"text-xs text-gray-500
  mt-1\">Slide left for Concave (Inward), right for Convex
  (Outward)</p>                 </div>                 <div>                     \
  <label class=\"block text-sm font-medium text-gray-700 mb-2\">Arc Vertical
  Position (Middle Point Y)</label>                     <input type=\"range\"
  id=\"mid_y\" min=\"10\" max=\"90\" value=\"50\" class=\"w-full\"
  oninput=\"updatePath()\">                 </div>             </div>              \
  <div class=\"bg-gray-800 rounded-lg p-4 relative\">                 <div
  class=\"flex justify-between items-center mb-2\">                     <span
  class=\"text-gray-400 text-sm font-mono\">SVG Path
  Code:</span>                     <button onclick=\"copyCode()\" id=\"copyBtn\"
  class=\"bg-blue-600 hover:bg-blue-700 text-white text-xs px-3 py-1 rounded
  transition\">Copy Code</button>                 </div>                 <code
  id=\"codeOutput\" class=\"text-green-400 text-sm font-mono break-all\">M0,0
  Q100,50 0,100 Z</code>             </div>             <p class=\"text-sm
  text-gray-500 mt-2\">Paste this directly into the <strong>Hero SVG Curve
  Path</strong> field in the CMS.</p>         </div>          <!-- Right: Visual
  Preview -->         <div class=\"bg-gray-100 rounded-xl flex items-center
  justify-center p-8 relative overflow-hidden h-[600px] border
  border-gray-200\">             <!-- Simulated \"Left Block\"
  -->             <div class=\"absolute left-0 top-0 bottom-0 w-1/4
  bg-[#114B5F]\"></div>                          <!-- SVG Canvas
  -->             <svg viewBox=\"0 0 100 100\" class=\"w-full h-full
  overflow-visible z-10\" preserveAspectRatio=\"none\">                 <!-- The
  actual filled shape using a pure Quadratic Bezier Curve (Q)
  -->                 <path id=\"curvePath\" d=\"M0,0 Q100,50 0,100 Z\"
  fill=\"#114B5F\" />                                  <!-- Visual Control
  Points -->                 <circle id=\"p_top\" cx=\"0\" cy=\"0\" r=\"3\"
  fill=\"#ef4444\" />                 <circle id=\"p_mid\" cx=\"50\" cy=\"50\"
  r=\"3\" fill=\"#3b82f6\" />                 <circle id=\"p_bot\" cx=\"0\"
  cy=\"100\" r=\"3\" fill=\"#ef4444\"
  />             </svg>         </div>     </div>      <script>         function
  updatePath() {             const mid_x =
  parseInt(document.getElementById('mid_x').value);             const mid_y =
  parseInt(document.getElementById('mid_y').value);              // To calculate
  the invisible control point needed for a perfect Q arc,             // we have
  to find the straight line between the top and bottom at exactly
  X=0.             // Then we push the control point out twice as far from that
  line as our desired mid_x point.                          const
  line_x_at_mid_y = 0; // The line is completely flat at X=0             const
  cx = line_x_at_mid_y + (2 * (mid_x - line_x_at_mid_y));             const cy =
  mid_y;              // Construct the perfect, full-height path             //
  M0,0 (Start top left) -> Q(ControlPoint) -> 0,100 (End bottom left) -> Z
  (Close)             const pathData = `M0,0 Q${cx},${cy} 0,100
  Z`;              // Update
  UI             document.getElementById('curvePath').setAttribute('d',
  pathData);             document.getElementById('codeOutput').textContent =
  pathData;              // Update visual
  dots             document.getElementById('p_top').setAttribute('cx',
  0);             document.getElementById('p_mid').setAttribute('cx',
  mid_x);             document.getElementById('p_mid').setAttribute('cy',
  mid_y);             document.getElementById('p_bot').setAttribute('cx',
  0);         }          function copyCode() {             const text =
  document.getElementById('codeOutput').textContent;             navigator.clip\
  board.writeText(text).then(() => {                 const btn =
  document.getElementById('copyBtn');                 btn.textContent =
  'Copied!';                 btn.classList.replace('bg-blue-600',
  'bg-green-600');                 setTimeout(() =>
  {                     btn.textContent = 'Copy
  Code';                     btn.classList.replace('bg-green-600',
  'bg-blue-600');                 },
  2000);             });         }          //
  Initialize         updatePath();     </script> </body> </html> EOF"
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
