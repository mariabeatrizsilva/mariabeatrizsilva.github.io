---
title: "Geometry Remesher: Algorithmic Optimization of 3D Meshes"
excerpt: "Making messy 3D meshes nice and uniform again."
layout: single
permalink: /projects/geometry-remesher/
author_profile: true
classes: wide
header:
  image: /assets/images/remesher_preview.png
  teaser: /assets/images/remesher_teaser.png
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

## Overview

This project implements an adaptive remeshing pipeline based on the algorithm from Alliez et al. (2002) to generate uniform, high-quality re-triangulations of 3D models. The remesher takes irregular triangle meshes with varying triangle sizes and densities and reorganizes them into clean, uniform meshes with well-shaped equilateral triangles.

---

## The Problem

3D meshes often have quality issues:
- Triangles of vastly different sizes
- Poor triangle shapes (long, thin triangles instead of equilateral ones)
- Uneven vertex distribution
- Irregular tessellation that makes further processing difficult

These issues arise from 3D scanning, modeling software, or mesh simplification algorithms. A high-quality remesh with uniform, equilateral triangles is essential for numerical simulations, rendering, and further geometric processing.

---

## Algorithm Pipeline

The remeshing process follows five key steps:

### **1. Harmonic Parameterization**
Map the 3D mesh onto a 2D circular domain using harmonic parameterization. This flattening operation preserves local geometric relationships while creating a workable 2D space.

### **2. Area Density Map Construction**
Compute an area density map that captures how much the original mesh was stretched or compressed during the flattening process. This map guides where we need higher or lower vertex density in the remeshed result.

### **3. Vertex Resampling**
Use an error diffusion algorithm with a Bayer kernel to place new vertices across the flattened surface. The density map ensures points are distributed proportionally to the original mesh's geometric complexity—more points in areas of high curvature or detail, fewer in flat regions.

### **4. 2D Delaunay Triangulation**
Connect the resampled vertices using 2D Delaunay triangulation, which maximizes the minimum angle of triangles and produces well-shaped triangles in the parametric domain.

### **5. Inverse Mapping to 3D**
Map the new 2D triangulation back to 3D space using the inverse of the harmonic parameterization. The result is a clean, uniformly remeshed 3D model that approximates the original geometry with better triangle quality.

---

## Implementation Details

**Language:** Python  
**Key Libraries:**
- `scipy` - 2D Delaunay triangulation
- `libigl` - Mesh I/O, harmonic parameterization, and mesh operations
- `numpy` - Numerical computations

**Structure:**
- Core remeshing algorithm packaged as a reusable `Remesher` class in `remesher.py`
- Interactive Jupyter notebook with step-by-step visualization of each pipeline stage
- Modular design allows easy experimentation with different density maps and sampling strategies

---

## Key Features

- **Adaptive Density Control**: Remeshing respects the geometric complexity of the original mesh
- **Quality Optimization**: Produces near-equilateral triangles for improved numerical stability
- **Modular Pipeline**: Each stage can be independently modified or replaced
- **Visual Debugging**: Jupyter notebook workflow enables inspection of intermediate results

---

## Technical Challenges

**Harmonic Parameterization**: Ensuring the 2D mapping preserves enough geometric information while remaining computationally stable.

**Density Map Accuracy**: Balancing between faithful reproduction of original detail and achieving uniform triangle shapes.

**Boundary Handling**: Managing mesh boundaries during parameterization and ensuring valid triangulation.

---

## Results

The remesher successfully transforms irregular input meshes into clean, uniform triangulations while preserving the overall shape and important geometric features. The quality of output triangles is significantly improved, with most triangles approaching equilateral shape.

---

## Future Improvements

- Extend to handle meshes with boundaries more robustly
- Implement feature-aware remeshing that preserves sharp edges
- Add support for anisotropic remeshing (elongated triangles aligned with principal curvature directions)
- Optimize performance for large meshes

---

[View on GitHub](https://github.com/mariabeatrizsilva/GeometryRemesher)

**Technologies:** Python • NumPy • SciPy • libigl