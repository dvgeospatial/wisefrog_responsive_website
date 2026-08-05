---
title: Canopy map
layout: layouts/portfolio-entry.njk
tags:
  - portfolio
permalink: /portfolio/canopy-map/
summary: ""
hero_image: /assets/images/screenshot_2026-07-16_15-05-45.webp
blocks:
  - type: text
    body: Wisefrog's Canopy map layer captures height, location and canopy/crown
      extents of all trees and hedges in urban and rural areas above 1m in
      height. Designed to support habitat management and conservation, it
      provides land managers and environmental projects with an at-a-glance view
      of vegetation structure within a land holding or landscape.Explore our
      interactive demo of the trees of Norwich below to see the CanopyMap in
      action.
    heading: "Canopy Map: every tree and hedge mapped"
  - type: embed
    embed_type: iframe
    embed_url: https://canopymapnorwich.netlify.app/
  - type: text
    body: >-
      The foundation of the CanopyMap is the Environment Agency’s National LiDAR
      Programme data. Between 2017 and 2023, specially equipped planes flew
      across England, bouncing laser pulses off the landscape to achieve
      complete, 1-meter resolution coverage of the country. While the primary
      goal was to help predict flood risks and manage coastal erosion, this rich
      dataset has incredible value for conservation.


      To isolate the vegetation, our mapping process compares two different digital layers: a map of the bare earth and a surface map showing the tops of everything sitting on the ground. By subtracting the ground level from the overall height, we effectively strip away the terrain to reveal the true heights of the objects above it. The data is then carefully filtered to focus entirely on plants and trees. Finally, a precise digital boundary is drawn around the leafy canopy of each tree, calculating the exact peak height to create a comprehensive landscape profile.


      Explore our interactive demos below to see the CanopyMap in action, featuring 3D hedge profiles, pond shading analysis, and hedgerow classifications across sample field parcels.
    heading: How we built the Canopy Map
  - body: >-
      Canopy map is derived from the Environment Agency’s National LIDAR
      Programme data which models the terrain and surface features for all of
      England.


      To isolate the vegetation for Canopy map, our mapping process compares two different digital layers: a map of the bare earth and a surface map showing the tops of everything sitting on the ground. By subtracting the ground level from the overall height, we effectively strip away the terrain to reveal the true heights of the objects above it. The data is then filtered to remove buildings and other features such as solar farms.  Finally, a precise digital boundary is drawn around the leafy canopy of each tree, calculating the exact peak height to create a comprehensive landscape profile.
---
