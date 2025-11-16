---
title: "Projects"
layout: archive
permalink: /projects/
author_profile: true
comments: true
---

<div class="projects-grid">

<div class="project-card">
<div class="card-image">
<img src="/assets/images/remesher_teaser.png" alt="Geometry Remesher">
</div>
<div class="card-content">
<h3>Geometry Remesher</h3>
<p class="card-course">Geometric Modeling</p>
<p class="card-description">Implementation of the Alliez et al. remeshing pipeline to generate uniform, high-quality re-triangulations of 3D models.</p>
<p class="card-tech">Python • NumPy • LibIGL</p>
<div class="card-links">
<a href="https://github.com/mariabeatrizsilva/GeometryRemesher">GitHub</a>
<a href="/projects/geometry-remesher/">Case Study</a>
</div>
</div>
</div>

<div class="project-card">
<div class="card-image">
<img src="/assets/images/cup-preview.png" alt="Murano Glass Cup">
</div>
<div class="card-content">
<h3>Murano Glass Cup</h3>
<p class="card-course">Intro to Computer Graphics</p>
<p class="card-description">Recreating murano glass and its unique patterns using procedural texturing and advanced shading techniques.</p>
<p class="card-tech">OpenGL • GLSL</p>
<div class="card-links">
<a href="https://github.com/mariabeatrizsilva/murano">GitHub</a>
</div>
</div>
</div>

<!-- Template for more projects -->
<div class="project-card">
<div class="card-image">
<img src="/assets/images/placeholder.png" alt="Project">
</div>
<div class="card-content">
<h3>Project Title</h3>
<p class="card-course">Context</p>
<p class="card-description">Brief description of what this project does.</p>
<p class="card-tech">Tech • Stack</p>
<div class="card-links">
<a href="#">GitHub</a>
</div>
</div>
</div>

</div>

<style>
.projects-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
    gap: 24px;
    max-width: 1000px;
    margin: 0 auto;
    padding: 20px 0;
}

.project-card {
    background: #fff;
    border: 1px solid #e0e0e0;
    border-radius: 12px;
    overflow: hidden;
    transition: transform 0.2s ease, box-shadow 0.2s ease;
    display: flex;
    flex-direction: column;
    height: 100%;
}

.project-card:hover {
    transform: translateY(-4px);
    box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
}

.card-image {
    width: 100%;
    height: 200px;
    overflow: hidden;
    background: #f8f8f8;
    display: flex;
    align-items: center;
    justify-content: center;
}

.card-image img {
    width: 100%;
    height: 100%;
    object-fit: cover;
}

.card-content {
    padding: 20px;
    display: flex;
    flex-direction: column;
    gap: 8px;
    flex-grow: 1;
}

.card-content h3 {
    margin: 0;
    font-size: 1.2rem;
    font-weight: 600;
    color: #333;
}

.card-course {
    font-size: 0.85rem;
    color: #888;
    font-style: italic;
    margin: 0;
}

.card-description {
    font-size: 0.9rem;
    line-height: 1.5;
    color: #555;
    margin: 4px 0;
    flex-grow: 1;
}

.card-tech {
    font-family: 'Courier New', monospace;
    font-size: 0.8rem;
    color: #666;
    margin: 8px 0 4px 0;
}

.card-links {
    display: flex;
    gap: 8px;
    flex-wrap: wrap;
    margin-top: 8px;
}

.card-links a {
    display: inline-block;
    padding: 6px 12px;
    border: 1px solid #333;
    border-radius: 4px;
    text-decoration: none;
    color: #333;
    font-size: 0.85rem;
    transition: all 0.2s ease;
}

.card-links a:hover {
    background: #333;
    color: #fff;
}

/* Responsive - single column on mobile */
@media (max-width: 768px) {
    .projects-grid {
        grid-template-columns: 1fr;
        gap: 20px;
    }
    
    .card-image {
        height: 180px;
    }
}
</style>