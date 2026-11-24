---
title: "Cook-Torrance Watch"
date: 2026-11-23 18:45:00
categories: rendering path tracing
excerpt: "A glTF reconstruction of the gold digital watch from Figure 8 of Cook and Torrance's A Reflectance Model for Computer Graphics"
tags: [metal, roughness, anisotropy, path tracing]
layout: default
comments: false
permalink: /blog/CookTorranceWatch
---

# {{page.title}}

<time datetime="{{ page.date | date_to_xmlschema }}">
  <em>{{ page.date | date: "%b %-d, %Y" }}</em>
</time>

This is my glTF reconstruction of the digital watch from Figure 8 of Cook and Torrance’s "A Reflectance Model for Computer Graphics". They credit Stuart Sechrest as a collaborator on the original watch.

There is a reconstructed the original model available for download, and also a modernized version with some extra light transport challenges and geometry detail.

<div style="overflow: hidden; margin: 20px 0;">
  <figure>
    <a href="{{site.baseurl}}/files/cook_torrance_watch/original.png">
      <img src="{{site.baseurl}}/files/cook_torrance_watch/original.png" alt="Cook-Torrance Watch with a gold bracelet and a red display reading 1981 above the SIGGRAPH label" loading="lazy">
    </a>
    <figcaption>Reconstruction of Figure 8</figcaption>
  </figure>
  <figure>
    <a href="{{site.baseurl}}/files/cook_torrance_watch/modern.png">
      <img src="{{site.baseurl}}/files/cook_torrance_watch/modern.png" alt="Modern version of Cook-Torrance Watch with a gold bracelet and a red display reading 1981 above the SIGGRAPH label" loading="lazy">
    </a>
    <figcaption>Modernized version</figcaption>
  </figure>
</div>

## The scene

- **Gold and steel.** The bracelet is gold on the outside and stainless steel on the inside. Gold and steel use different roughness, and I added a little anisotropy.
- **LED display.** The paper describes red LEDs with a dominant wavelength of **640 nm**. I converted a monochromatic 640 nm sample to linear sRGB. The seven-segment digits are geometry with a fine raster texture that varies their brightness.
- **Lighting.** A white disk in the blue environment map lights the watch. 

## Download

- <a href="{{site.baseurl}}/files/cook_torrance_watch/CookTorranceWatch.gltf" download>Download original scene (glTF)</a>
- <a href="{{site.baseurl}}/files/cook_torrance_watch/CookTorranceWatch_environment.exr" download>Download original environment map (EXR)</a>     

- <a href="{{site.baseurl}}/files/cook_torrance_watch/CookTorranceWatchModern.gltf" download>Download modern scene (glTF)</a>
- <a href="{{site.baseurl}}/files/cook_torrance_watch/CookTorranceWatchModern_environment.exr" download>Download modern environment map (EXR)</a>

## License and Citation

Reconstruction of geometry, environment map and textures is released under [CC0 1.0 Universal](https://creativecommons.org/publicdomain/zero/1.0/). If you use the scene in a paper, please cite the work that inspired it and optionally my reconstruction as well.

```bibtex
@article{cook1982reflectance,
  author  = {Cook, Robert L. and Torrance, Kenneth E.},
  title   = {A Reflectance Model for Computer Graphics},
  journal = {ACM Transactions on Graphics},
  volume  = {1},
  number  = {1},
  pages   = {7--24},
  year    = {1982},
  doi     = {10.1145/357290.357293}
}
```               

Citation for this reconstruction:

```bibtex
@misc{boksansky2026cookTorranceWatch,
  author       = {Bok{\v{s}}ansk{\'{y}}, Jakub},
  title        = {Cook Torrance Watch: A {glTF} Reconstruction},
  year         = {2026},
  url          = {https://boksajak.github.io/blog/CookTorranceWatch},
  note         = {Reconstruction of the scene shown in Figure 8
                  of Cook and Torrance’s A Reflectance Model for Computer Graphics}
}
```