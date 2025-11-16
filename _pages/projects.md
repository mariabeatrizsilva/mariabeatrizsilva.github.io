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
<img src="/assets/images/geneva_teaser.png" alt="GeneVA Dataset">
</div>
<div class="card-content">
<h3>GeneVA: Human Annotations for Generative Video Quality</h3>
<p class="card-course">Research Project • WACV 2026</p>
<p class="card-description">Co-authored dataset capturing human perception of visual quality in AI-generated videos. Implemented end-to-end data pipeline, developed infrastructure, and authored related works section.</p>
<p class="card-tech">Python • Hugging Face APIs • Perceptual Quality Assessment</p>
<div class="card-links">
<a href="https://arxiv.org/abs/2509.08818">arXiv</a>
<a href="/projects/geneva/">Project Details</a>
</div>
</div>
</div>


<div class="project-card">
<div class="card-image">
<img src="/assets/images/remesher_teaser.png" alt="Geometry Remesher">
</div>
<div class="card-content">
<h3>Geometry Remesher</h3>
<p class="card-course">Geometric Modeling (Graduate Level)</p>
<p class="card-description">Implementation of the Alliez et al. remeshing pipeline to generate uniform, high-quality re-triangulations of 3D models.</p>
<p class="card-tech">Python • NumPy • LibIGL</p>
<div class="card-links">
<a href="https://github.com/mariabeatrizsilva/GeometryRemesher">GitHub</a>
<a href="/projects/geometry-remesher/">Project Details</a>
</div>
</div>
</div>


<div class="project-card">
<div class="card-image">
<img src="/assets/images/deformer-teaser.png" alt="Laplacian Mesh Deformer">
</div>
<div class="card-content">
<h3>Laplacian Mesh Deformer</h3>
<p class="card-course">Geometric Modeling (Graduate Level)</p>
<p class="card-description">Interactive 3D mesh deformation system that preserves high-frequency geometric details using multiresolution Laplacian editing and sparse Cholesky decomposition for near real-time performance.</p>
<p class="card-tech">Python • SciPy • libigl • Sparse Cholesky</p>
<div class="card-links">
<a href="https://github.com/mariabeatrizsilva/LaplacianDeformer">GitHub</a>
<a href="/projects/laplacian-deformer/">Project Details</a>
</div>
</div>
</div>

<div class="project-card">
<div class="card-image">
<img src="/assets/images/fine_tuning_llm_teaser.png" alt="Fine-Tuning Language Models">
</div>
<div class="card-content">
<h3>Fine-Tuning Language Models</h3>
<p class="card-course">Natural Language Processing (Graduate Level)</p>
<p class="card-description">Fine-tuned BERT for sentiment classification with robustness testing and T5 for natural language to SQL translation, implementing evaluation pipelines and data augmentation strategies.</p>
<p class="card-tech">Python • PyTorch • Hugging Face • BERT • T5</p>
<div class="card-links">
<a href="https://github.com/mariabeatrizsilva/FineTuningLMs">GitHub</a>
<a href="/projects/fine_tuning_lm/">Project Details</a>
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
/* Override theme container constraints */
.page__content {
    max-width: 100% !important;
    padding: 0 !important;
}

.archive {
    padding: 0 !important;
}

.projects-list {
    width: 100%;
    max-width: 100%;
    margin: 0;
    padding: 0;
    display: flex;
    flex-direction: column;
    gap: 20px;
}

.project-card {
    background: #fff;
    border: 1px solid #e0e0e0;
    border-radius: 8px;
    overflow: hidden;
    display: flex;
    flex-direction: row;
    transition: transform 0.2s ease, box-shadow 0.2s ease;
}

.project-card:hover {
    transform: translateY(-2px);
    box-shadow: 0 4px 12px rgba(0, 0, 0, 0.08);
}

.card-image {
    width: 240px;
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
    object-fit: contain; 
    object-position: center;
}

.card-content {
    padding: 20px 24px;
    display: flex;
    flex-direction: column;
    gap: 6px;
    flex-grow: 1;
}

.card-content h3 {
    margin: 0;
    font-size: 1.1rem;
    font-weight: 600;
    color: #333;
}

.card-course {
    font-size: 0.8rem;
    color: #888;
    font-style: italic;
    margin: 0;
}

.card-description {
    font-size: 0.85rem;
    line-height: 1.5;
    color: #555;
    margin: 4px 0;
}

.card-tech {
    font-family: 'Courier New', monospace;
    font-size: 0.75rem;
    color: #666;
    margin: 4px 0 10px 0;
}

.card-links {
    display: flex;
    gap: 8px;
    flex-wrap: wrap;
}

.card-links a {
    display: inline-block;
    padding: 6px 14px;
    background: #f0f0f0;
    border-radius: 16px;
    text-decoration: none;
    color: #333;
    font-size: 0.8rem;
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
        height: 180px;
    }
    
    .card-content {
        padding: 16px;
    }
}
</style>