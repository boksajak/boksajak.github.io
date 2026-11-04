---
title: "Cornell Box 2026"
date: 2026-11-04 19:52:45
categories: rendering raytracing
excerpt: ""
tags: [cornell box path tracing]
layout: default
comments: false
permalink: /blog/:title
---

# {{page.title}}

<time datetime="{{ page.date | date_to_xmlschema }}">
  <em>{{ page.date | date: "%b %-d, %Y" }}</em>
</time>

Here is a "Cornell Box 2026" GLTF scene - your good old Cornell Box with some light transport challenges added: normal maps, scratched and curved anodized anisotropic metal plate with iridescence, small light source surrounded by thin geometry and a thick glass block with many internal reflections throwing caustics. Ceramic block has a little recess for indirect lighting. There is also an environment map inspired by Figure 1 in Bruce Walter's "Microfacet Models for Refraction through Rough Surfaces".

[![Cornell Box 2026: front view of the scene]({{site.baseurl}}/files/cornell_box_2026/render_front_crop.png)]({{site.baseurl}}/files/cornell_box_2026/render_front_crop.png)

## The scene

The scene brings several rendering challenges:

- **Slatted pendant light.** An emissive source inside the shade casts a pattern of narrow shadows across the ceiling and walls.
- **Glazed ceramic.** A tall block combines decorative relief, a recessed opening, and varying surface roughness, providing a contrast between diffuse shading and glossy highlights.
- **Iridescent metal.** The curved metal sheet combines anisotropic reflection with thin-film iridescence. Its changing surface orientation creates the angular variation in reflections and color.
- **Solid glass.** A rounded glass block exercises refraction, Fresnel reflection, total internal reflection, absorption, and caustics. Its beveled edges provide additional paths through the material.

The red and green walls provide a familiar setting for inspecting color bleeding and indirect illumination - and are now normal mapped with carpet-like structure.

## Renders

Path traced with BSDF sampling only (no NEE) and up to 64 bounces using Russian Roulette.

<div style="overflow: hidden; margin: 20px 0;">
  <figure>
    <a href="{{site.baseurl}}/files/cornell_box_2026/render_front.png">
      <img src="{{site.baseurl}}/files/cornell_box_2026/render_front.png" alt="Cornell Box 2026: full front view" loading="lazy">
    </a>
    <figcaption>Front view</figcaption>
  </figure>
  <figure>
    <a href="{{site.baseurl}}/files/cornell_box_2026/render_wide.png">
      <img src="{{site.baseurl}}/files/cornell_box_2026/render_wide.png" alt="Cornell Box 2026: wide view" loading="lazy">
    </a>
    <figcaption>Wide view</figcaption>
  </figure>
</div>

<div style="overflow: hidden; margin: 20px 0;">
  <figure>
    <a href="{{site.baseurl}}/files/cornell_box_2026/render_detail.png">
      <img src="{{site.baseurl}}/files/cornell_box_2026/render_detail.png" alt="Cornell Box 2026: detail view" loading="lazy">
    </a>
    <figcaption>Detail view</figcaption>
  </figure>
  <figure>
    <a href="{{site.baseurl}}/files/cornell_box_2026/render_caustics.png">
      <img src="{{site.baseurl}}/files/cornell_box_2026/render_caustics.png" alt="Cornell Box 2026: caustics view" loading="lazy">
    </a>
    <figcaption>Caustics view</figcaption>
  </figure>
</div>

## Download

Scene files and download details will be added here.


## Citation

If you use this scene in your work, please cite:

```bibtex
@misc{boksansky2026cornellbox,
  author = {Bok{\v{s}}ansk{\'{y}}, Jakub},
  title  = {{Cornell Box 2026}},
  year   = {2026},
  url    = {https://boksajak.github.io/blog/CornellBox}
}
```
