---
title: "Geometry Remesher: Algorithmic Optimization of 3D Meshes"
excerpt: "Implementation of the Alliez et al. remeshing pipeline using Python and Jupyter Notebooks to generate uniform, high-quality re-triangulations of 3D models."
header:
  image: /assets/images/remesher_preview.png 
  teaser: /assets/images/remesher_teaser.jpg 
categories:
  - Portfolio
tags:
  - Python
  - Computational Geometry
  - Jupyter
  - Algorithm Implementation
  - igl (libigl)
---

# Geometry Remesher: Algorithmic Optimization of 3D Meshes

## Project Summary 🎯

This project implements the sophisticated geometry remeshing pipeline introduced by Alliez et al. (2002). The goal is to transform existing, potentially irregular 3D meshes into a new mesh composed of more **uniform (equilateral) and better-distributed triangles**. This optimization is crucial for efficient downstream applications in graphics and simulation.

The entire workflow is demonstrated within a **Jupyter Notebook (`Remesher_v4.ipynb`)**, with the core logic encapsulated within a **Python class (`remesher.py`)**.

## My Role and Contribution 🛠️

I implemented the complete five-step remeshing pipeline in **Python**, leveraging libraries like `scipy` and `igl` (libigl). My contributions included:
* **Translating theory to code:** Implementing the complex geometric algorithms (such as Harmonic Parameterization and Error Diffusion) into a functional, reusable Python class.
* **Workflow Development:** Structuring the process within a Jupyter Notebook for clear execution, visualization, and parameter exploration.
* **Algorithmic Exploration:** Testing and visualizing the impact of different parameters (e.g., grid size, dithering methods) on the final mesh quality.

## The Five-Step Remeshing Pipeline 💡

The core of the project is the sequential execution of these five steps, which transform the 3D model through a 2D intermediate space:

1.  **Parameterization:** The 3D input mesh is mapped onto a **2D parameter space** using **Harmonic Parameterization** ($H$). This creates a smooth, bijective mapping onto a 2D circle.
2.  **Map Generation:** An **Area Map ($\mathcal{M}_{A}$)** is computed over the 2D space. This map encodes geometric distortion, which is later used to correct the density of sampling points.
3.  **Sampling Point Generation:** New vertices are determined by applying a **halftoning/error-diffusion algorithm** (using the Bayer kernel) to the Area Map. This scatters points non-uniformly across the 2D space, respecting the target density defined by the map.
4.  **2D Triangulation:** A **2D Delaunay triangulation** (using `scipy.spatial.Delaunay`) is applied to connect the newly sampled 2D points, forming the faces of the new mesh.
5.  **3D Mesh Reconstruction:** The 2D vertices and faces are mapped back onto the original 3D surface using the **inverse of the Harmonic Parameterization ($H^{-1}$)**, yielding the final, optimized 3D model.

## Results and Skills Demonstrated ✨

This project effectively demonstrates proficiency in:
* **Computational Geometry:** Deep understanding and implementation of complex geometric algorithms.
* **Python Development:** Building reusable class structures for complex pipelines.
* **Data Processing:** Efficient handling of 3D mesh data using specialized libraries (`igl`, `scipy`).
* **Visualization and Analysis:** Using Jupyter Notebooks to explore parameters and visualize intermediate results (e.g., Area Maps, different dithering effects).

---
*View the full source code, data, and implementation notebook on [GitHub](https://github.com/mariabeatrizsilva/GeometryRemesher).*

***