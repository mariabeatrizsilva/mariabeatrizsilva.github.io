---
title: "Projects"
layout: archive
permalink: /projects/
author_profile: true
comments: true
---

<div class="projects-container">

<div class="project-item">
<div class="project-image">
<img src="/assets/images/remesher_teaser.png" alt="Geometry Remesher">
</div>
<div class="project-content">
<h3>Geometry Remesher</h3>
<p class="project-course">Geometric Modeling (graduate level)</p>
<p class="project-description">Implementation of the Alliez et al. remeshing pipeline using Python to generate uniform, high-quality re-triangulations of 3D models.</p>
<p class="project-tech">Tech: Python, NumPy, LibIGL</p>
<div class="project-links">
<a href="https://github.com/mariabeatrizsilva/GeometryRemesher">GitHub</a>
<a href="/projects/geometry-remesher/">Case Study</a>
</div>
</div>
</div>

<div class="project-item">
<div class="project-image">
<img src="/assets/images/cup-preview.png" alt="Murano Glass Cup">
</div>
<div class="project-content">
<h3>Murano Glass Cup</h3>
<p class="project-course">Introduction to Computer Graphics</p>
<p class="project-description">A project focused on recreating the look of murano glass and its unique patterns using procedural texturing and advanced shading techniques.</p>
<p class="project-tech">Tech: WebGL, Procedural texturing, JavaScript</p>
<div class="project-links">
<a href="https://github.com/mariabeatrizsilva/murano">GitHub</a>
</div>
</div>
</div>

<!-- Add more projects here -->
<!-- <div class="project-item">
<div class="project-image">
<img src="/assets/images/placeholder.png" alt="Project Title">
</div>
<div class="project-content">
<h3>Your Next Project</h3>
<p class="project-course">Context or course name</p>
<p class="project-description">Description of what this project does and why it's cool.</p>
<p class="project-tech">Tech: Your, Tech, Stack</p>
<div class="project-links">
<a href="https://github.com/yourusername/project">GitHub</a>
</div>
</div>
</div> -->

</div>

<style>
.projects-container {
    max-width: 800px;
    margin: 0 auto;
}

.project-item {
    display: flex;
    gap: 30px;
    margin-bottom: 60px;
    padding-bottom: 60px;
    border-bottom: 1px solid #e0e0e0;
}

.project-item:last-child {
    border-bottom: none;
}

.project-image {
    flex-shrink: 0;
    width: 250px;
}

.project-image img {
    width: 100%;
    height: auto;
    border-radius: 4px;
}

.project-content {
    flex: 1;
    display: flex;
    flex-direction: column;
    gap: 8px;
}

.project-content h3 {
    margin: 0 0 4px 0;
    font-size: 1.4rem;
    font-weight: 600;
}

.project-course {
    font-size: 0.9rem;
    color: #666;
    font-style: italic;
    margin: 0;
}

.project-description {
    margin: 8px 0;
    line-height: 1.6;
    color: #444;
}

.project-tech {
    font-family: 'Courier New', monospace;
    font-size: 0.85rem;
    color: #666;
    margin: 4px 0 12px 0;
}

.project-links {
    display: flex;
    gap: 12px;
    flex-wrap: wrap;
}

.project-links a {
    display: inline-block;
    padding: 6px 14px;
    border: 1px solid #333;
    border-radius: 3px;
    text-decoration: none;
    color: #333;
    font-size: 0.9rem;
    transition: all 0.2s ease;
}

.project-links a:hover {
    background: #333;
    color: #fff;
}

/* Mobile responsive */
@media (max-width: 768px) {
    .project-item {
        flex-direction: column;
        gap: 20px;
        margin-bottom: 40px;
        padding-bottom: 40px;
    }
    
    .project-image {
        width: 100%;
    }
}
</style>