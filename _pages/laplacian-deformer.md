---
title: "Laplacian Deformer"
excerpt: "Making messy 3D meshes nice and uniform again."
layout: single
permalink: /projects/laplacian-deformer/
author_profile: true
classes: wide
header:
  image: /assets/images/deformer-preview.png
  teaser: /assets/images/deformer-teaser.png
---

<style>
.page__hero {
    max-height: 350px !important;
    overflow: hidden;
}
.page__hero-image {
    max-height: 350px !important;
    object-fit: contain;
}
</style>

**Course Project for Geometric Modeling (Graduate Level)**  
**Spring 2025**

[📂 GitHub Repository](https://github.com/mariabeatrizsilva/GeometryRemesher)

---

## Project Overview

This project implements a **Multiresolution Laplacian Mesh Deformer**, a technique used to manipulate 3D models interactively while preserving their high-frequency geometric details.

This implementation is based on course content from _Professor Daniele Panozzo (NYU)_, who provided the initial setup, including the iPyWidget used in the `DeformExample.ipynb` notebook for interactive visualization and the `Selection.ipynb` that is used to add handles to a mesh.


<div style="display: flex; gap: 10px; margin: 2rem 0; flex-wrap: wrap; justify-content: center;">
  <div style="flex: 1; min-width: 280px; max-width: 350px;">
    <video width="100%" controls>
      <source src="/assets/images/hand-move.mp4" type="video/mp4">
      Your browser does not support the video tag.
    </video>
    <p style="text-align: center; font-size: 0.85rem; color: #666; margin-top: 0.5rem; font-style: italic;">
      Hand deformation example
    </p>
  </div>
  
  <div style="flex: 1; min-width: 280px; max-width: 350px;">
    <video width="100%" controls>
      <source src="/assets/images/woody-dance.mp4" type="video/mp4">
      Your browser does not support the video tag.
    </video>
    <p style="text-align: center; font-size: 0.85rem; color: #666; margin-top: 0.5rem; font-style: italic;">
      Real-time interaction
    </p>
  </div>
  </div>

## Multiresolution Mesh Editing Pipeline

The overall deformation process is divided into three main phases to achieve detail-preserving manipulation, carried out by methods of the initialized deformer_ instance. The instance is initialized with the original mesh vertices ($V$), faces ($F$), and the indices of the control handles.

1. _Remove High-Frequency Details (Smoothing):_ The original mesh vertices ($V$) are smoothed to create a low-frequency base mesh ($B$) by solving a Bilaplacian minimization problem.

`B = deformer_.smooth_mesh(v)`

2. _Compute Detail Encoding:_ The high-frequency details ($\text{details} = V - B$) are calculated and encoded in a local, orthogonal reference frame for each vertex. This frame is defined by the per-vertex normal ($\mathbf{n}$) and two tangent vectors ($\mathbf{x}$ and $\mathbf{y}$).

```
coeffs, tangents = deformer_.compute_detail_encoding(B)
```


3. _Deform the Smooth Mesh and Transfer Details:_ The low-frequency base mesh ($B$) is deformed based on the user-defined handle movement (`new_pos`) to create the new base mesh ($B'$). The stored detail coefficients are then applied to the new reference frames in $B'$ and added back to compute the final, detail-preserved deformed surface ($S'$).

```
B_prime = deformer_.smooth_mesh(new_pos) # Deformation of the smooth mesh
B_prime_dets = deformer_.apply_detail_encoding(B_prime, coeffs, tangents) # Detail transfer
S_prime = B_prime + B_prime_dets # Final result
```