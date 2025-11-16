---
title: "Geometry Remesher"
excerpt: "Making messy 3D meshes nice and uniform again."
layout: single
permalink: /projects/geometry-remesher/
date: 2025-11-15 10:00:00 -0400 
header:
  image: /assets/images/remesher_preview.png 
  teaser: /assets/images/remesher_teaser.png 
categories:
  - Portfolio
tags:
  - Python
  - Computational Geometry
---
<style>
/* Target the header image specifically */
.page__hero {
    max-height: 350px !important;
    overflow: hidden;
}

.page__hero-image {
    max-height: 350px !important;
    object-fit: cover;
}

/* Alternative: if the above doesn't work, try these */
/* header.page__hero--overlay {
    max-height: 350px !important;
}

.page__hero--overlay .page__hero-image {
    max-height: 350px !important;
} */
</style>
<!-- <img src="/assets/images/remesher_preview.png" alt="Remesher visualization" style="max-width: 700px; width: 100%; border-radius: 6px; margin: 0 auto 2rem auto; display: block;"> -->


# Geometry Remesher

## What it does

This project takes 3D meshes and cleans them up. Sometimes meshes can be messy—triangles of all different sizes, weird angles, uneven distribution. This remesher reorganizes everything into nice, uniform, equilateral triangles.

I followed the approach from a paper by Alliez et al. (2002), implementing the whole pipeline in Python. Everything lives in a Jupyter notebook so you can see the process step by step.

## How it works

The remeshing happens in five steps:

**1. Flatten it out**  
First, I map the 3D mesh onto a 2D circle using harmonic parameterization. 

**2. Make an area density map**  
I then create a map that shows where the original mesh was stretched or compressed during flattening. This helps us know where we need more or fewer points later.

**3. Scatter new points**  
Using an error diffusion algorithm (with a Bayer kernel), I place new vertices across the flattened surface. The density map ensures points are distributed in accordance to the area map.

**4. Connect the dots**  
I run a 2D Delaunay triangulation to connect all the new points into triangles.

**5. Wrap it back**  
Finally, I map everything back to 3D using the inverse of the original parameterization. Now you have a clean, remeshed 3D model.

## Tech

Built with Python, using `scipy` for triangulation and `libigl` for mesh handling. The whole thing is packaged as a reusable class in `remesher.py`, with examples in a Jupyter notebook.

---

[View on GitHub](https://github.com/mariabeatrizsilva/GeometryRemesher)