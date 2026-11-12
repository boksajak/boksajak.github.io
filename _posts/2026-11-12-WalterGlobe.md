---
title: "Walter Globe"
date: 2026-11-12 09:45:00
categories: rendering path tracing
excerpt: "A rough glass globe inspired by Walter et al.'s microfacet refraction paper"
tags: [glass, refraction, microfacet, path tracing]
layout: default
comments: false
permalink: /blog/WalterGlobe
---

# {{page.title}}

<time datetime="{{ page.date | date_to_xmlschema }}">
  <em>{{ page.date | date: "%b %-d, %Y" }}</em>
</time>

Here is my reconstruction of a "Walter Globe" scene - a glass globe from Figure 1 in ["Microfacet Models for Refraction through Rough Surfaces"](https://www.cs.cornell.edu/~srm/publications/EGSR07-btdf.html) by Bruce Walter et al. The striped environment in my [Cornell Box 2026]({{site.baseurl}}/blog/CornellBox2026) was already inspired by this image, so I decided to try recreating the globe as well.

The original scene and image credit belongs to the paper's authors. This is an approximate reconstruction from the Figure 1 published in a paper.

[![Walter Globe: wider view of the rough glass globe]({{site.baseurl}}/files/walter_globe/render_zoomout.png)]({{site.baseurl}}/files/walter_globe/render_zoomout.png)

## The scene

The scene brings several rendering challenges:

- **Rough glass.** A solid glass sphere combines reflection and refraction with spatially varying roughness. The continents are rougher than the oceans - their shapes come entirely from the roughness texture. Ocean roughness is 0.1 and land roughness is 0.3, using glTF's GGX convention. Note that original figure used Beckmann roughness but I used GGX which is more common nowadays. The index of refraction is 1.5 (average glass).
- **Striped backdrop.** Narrow colored and black stripes make the distortion and blur from rough transmission easy to see. The globe itself has no intentional absorption tint.
- **Caustics.** A rectangular light above the globe produces a bright caustic on the floor.
- **Camera and placement.** The scene includes two 30-degree vertical-FOV cameras: **ZoomOut**, the default wider framing, and **PaperMatch**, the tighter framing fitted closer to the paper figure.

Light is a rectangle above the globe. The separate environment map is constant linear RGB **(0.4, 0.4, 0.4)**. If you want your render to be more contrasty like original Figure 1, reduce or remove the environment lighting.

## Renders

Path traced with BSDF sampling only (no NEE) and up to 48 bounces using Russian Roulette. 256,000 samples per pixel.


<div style="overflow: hidden; margin: 20px 0;">
  <figure>
    <a href="{{site.baseurl}}/files/walter_globe/render_zoomout.png">
      <img src="{{site.baseurl}}/files/walter_globe/render_zoomout.png" alt="Walter Globe: ZoomOut camera" loading="lazy">
    </a>
    <figcaption>ZoomOut - the default wider view</figcaption>
  </figure>
  <figure>
    <a href="{{site.baseurl}}/files/walter_globe/render_papermatch.png">
      <img src="{{site.baseurl}}/files/walter_globe/render_papermatch.png" alt="Walter Globe: PaperMatch camera" loading="lazy">
    </a>
    <figcaption>PaperMatch - tighter framing toward the original figure</figcaption>
  </figure>
</div>

## Download

- <a href="{{site.baseurl}}/files/walter_globe/WalterGlobe.gltf" download>Download scene (glTF)</a>
- <a href="{{site.baseurl}}/files/walter_globe/WalterGlobe_environment_0.4.exr" download>Download constant 0.4 environment map (EXR)</a>

## License and Citation

The Earth outlines use public-domain [Natural Earth land data](https://www.naturalearthdata.com/downloads/50m-physical-vectors/50m-land/).

The reconstruction, its included textures, and the environment map are released under [CC0 1.0 Universal](https://creativecommons.org/publicdomain/zero/1.0/). You may use, modify, and redistribute them, including for commercial purposes. Please credit the paper that inspired the scene, and optionally my reconstruction:

```bibtex
@inproceedings{walter2007microfacet,
  author    = {Walter, Bruce and Marschner, Stephen R. and Li, Hongsong and Torrance, Kenneth E.},
  title     = {Microfacet Models for Refraction through Rough Surfaces},
  booktitle = {Proceedings of the Eurographics Symposium on Rendering},
  year      = {2007},
  url       = {https://www.cs.cornell.edu/~srm/publications/EGSR07-btdf.html}
}
```

Citation for this reconstruction:

```bibtex
@misc{boksansky2026walterglobe,
  author       = {Bok{\v{s}}ansk{\'{y}}, Jakub},
  title        = {Walter Globe: A {glTF} Reconstruction},
  year         = {2026},
  url          = {https://boksajak.github.io/blog/WalterGlobe},
  note         = {Reconstruction of the scene shown in Figure 1
                  of Walter et al., Microfacet Models for
                  Refraction through Rough Surfaces (EGSR 2007)}
}
```
