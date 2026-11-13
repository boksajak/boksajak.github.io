---
title: "Whitted Spheres"
date: 2026-11-13 09:45:00
categories: rendering path tracing
excerpt: "A glTF reconstruction of the spheres from Turner Whitted's An Improved Illumination Model for Shaded Display"
tags: [glass, refraction, ray tracing, path tracing]
layout: default
comments: false
permalink: /blog/WhittedSpheres
---

# {{page.title}}

<time datetime="{{ page.date | date_to_xmlschema }}">
  <em>{{ page.date | date: "%b %-d, %Y" }}</em>
</time>

Here is another reconstruction of a classic scene from Figure 7 in ["An Improved Illumination Model for Shaded Display"](https://doi.org/10.1145/358876.358882) by Turner Whitted. 

The original scene and image credit belongs to Turner Whitted. This is an approximate reconstruction from the published images, using modern glTF materials.

[![Whitted Spheres with the studio environment]({{site.baseurl}}/files/whitted_spheres/render_studio.png)]({{site.baseurl}}/files/whitted_spheres/render_studio.png)

## The scene

The scene brings several rendering challenges:

- **Hollow glass.** The large sphere is actually hollow. My version uses two separate concentric sphere meshes with radii of 1.0 and 0.96 meters. The inner sphere has inward-facing normals, defining the glass-to-air boundary.
- **Reflection.** The smaller sphere combines sharp reflection with a diffuse white component. I used a metallic factor of 0.45 and zero roughness to approximate its appearance in the original image.
- **Checkerboard.** A finite red and yellow checkerboard makes the reflection and refraction easy to see. Each square is 0.5 meters wide.
- **Internal reflections and caustics.** Rays can reflect between the two glass surfaces before leaving the sphere. A path tracer also produces caustics on the floor.
- **Camera and placement.** The scene includes one camera, **Figure7**, with a **30-degree vertical FOV** and **4:3 aspect ratio**. The spheres follow the arrangement in the paper.

Note that scene will render differently with modern materials than in original paper. I have also preserved arrangement as published in the paper, which is available as black and white. The colors were matched from images in Whitted's presentations.

The hollow construction was discussed in Eric Haines's ["About that glass ball…"](https://www.realtimerendering.com/blog/about-that-glass-ball/).

The light is a distant white disk. The environment map contains a broad white softbox.

## Download

- <a href="{{site.baseurl}}/files/whitted_spheres/WhittedSpheres.gltf" download>Download scene (glTF)</a>
- <a href="{{site.baseurl}}/files/whitted_spheres/WhittedSpheres_environment.exr" download>Download environment map (EXR)</a>

## License and Citation


Please cite the paper that inspired the scene. The reconstruction, its included textures, environment maps, and procedural source are released under [CC0 1.0 Universal](https://creativecommons.org/publicdomain/zero/1.0/). You may use, modify, and redistribute them, including for commercial purposes. Attribution is appreciated but is not required under CC0.

```bibtex
@article{whitted1980illumination,
  author  = {Whitted, Turner},
  title   = {An Improved Illumination Model for Shaded Display},
  journal = {Communications of the ACM},
  volume  = {23},
  number  = {6},
  pages   = {343--349},
  year    = {1980},
  doi     = {10.1145/358876.358882}
}
```
