---
title: "Projects"
layout: archive
permalink: /projects/
author_profile: true
comments: true
---

<div class="projects-list">

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
<a href="#">Demo</a>
</div>
</div>
</div>

</div>

<style>
.projects-list {
    max-width: 900px;
    margin: 0 auto;
    padding: 20px 0;
    display: flex;
    flex-direction: column;
    gap: 24px;
}

.project-card {
    background: #fff;
    border: 1px solid #e0e0e0;
    border-radius: 12px;
    overflow: hidden;
    display: flex;
    flex-direction: row;
    transition: transform 0.2s ease, box-shadow 0.2s ease;
}

.project-card:hover {
    transform: translateY(-4px);
    box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
}

.card-image {
    width: 280px;
    flex-shrink: 0;
    background: #f8f8f8;
    display: flex;
    align-items: center;
    justify-content: center;
    overflow: hidden;
}

.card-image img {
    width: 100%;
    height: 100%;
    object-fit: cover;
}

.card-content {
    padding: 24px 28px;
    display: flex;
    flex-direction: column;
    gap: 8px;
    flex-grow: 1;
}

.card-content h3 {
    margin: 0;
    font-size: 1.3rem;
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
    font-size: 0.95rem;
    line-height: 1.6;
    color: #555;
    margin: 6px 0;
}

.card-tech {
    font-family: 'Courier New', monospace;
    font-size: 0.85rem;
    color: #666;
    margin: 4px 0 12px 0;
}

.card-links {
    display: flex;
    gap: 10px;
    flex-wrap: wrap;
}

.card-links a {
    display: inline-block;
    padding: 8px 18px;
    background: #f0f0f0;
    border-radius: 20px;
    text-decoration: none;
    color: #333;
    font-size: 0.9rem;
    font-weight: 500;
    transition: all 0.2s ease;
}

.card-links a:hover {
    background: #333;
    color: #fff;
    transform: translateY(-1px);
}

/* Mobile - stack vertically */
@media (max-width: 768px) {
    .project-card {
        flex-direction: column;
    }
    
    .card-image {
        width: 100%;
        height: 200px;
    }
    
    .card-content {
        padding: 20px;
    }
}
</style>