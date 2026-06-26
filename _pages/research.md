---
layout: page
title: Research
permalink: /research/
nav: true
nav_order: 2
---

My research develops physics-informed and data-driven methods to model,
estimate, and secure traffic dynamics across large-scale transportation
networks. The four directions below share a common foundation in network
traffic dynamics and a common methodological core in physics-informed learning,
optimization, game theory, and behavioral modeling.

{% include eh_research_map.liquid %}

<div class="eh-areas">
  {%- for p in site.data.research.pillars -%}
    <section class="eh-area" aria-label="{{ p.name }}">
      <div class="eh-area-head">
        <i class="{{ p.icon }} eh-area-icon" aria-hidden="true"></i>
        <h2 class="eh-area-name">{{ p.name }}</h2>
      </div>
      <div class="eh-area-intro">
        <p class="eh-area-desc">{{ p.description | default: p.blurb }}</p>
      </div>
      <figure class="eh-area-figure">
        <img
          class="eh-area-infographic"
          src="{{ '/assets/img/research/' | append: p.id | append: '.png' | relative_url }}"
          alt="{{ p.name }} research overview infographic"
          loading="lazy"
        >
      </figure>
      <div class="eh-area-papers">
        {%- for key in p.papers -%}
          {% bibliography --query @*[key={{ key }}] %}
        {%- endfor -%}
      </div>
    </section>
  {%- endfor -%}
</div>

<style>
  .eh-areas {
    margin: 2rem 0 0;
  }
  .eh-areas .eh-area {
    margin: 0 0 2.6rem;
  }
  .eh-areas .eh-area-head {
    display: flex;
    align-items: center;
    gap: 0.7rem;
    margin: 0 0 0.6rem;
    padding-bottom: 0.3rem;
    border-bottom: 2px solid var(--global-theme-color);
  }
  .eh-areas .eh-area-icon {
    font-size: 1.3rem;
    color: var(--global-theme-color);
    flex-shrink: 0;
  }
  .eh-areas .eh-area-name {
    font-size: 1.3rem;
    font-weight: 600;
    margin: 0;
    color: var(--global-text-color);
  }
  .eh-areas .eh-area-intro {
    margin: 0 0 1rem;
  }
  .eh-areas .eh-area-desc {
    margin: 0;
    line-height: 1.6;
    color: var(--global-text-color);
  }
  /* Infographic shown as a centered figure card, capped well below the body
     width so it reads as a supporting visual rather than dominating the
     section. The images have white backgrounds, so the white, rounded, padded
     card keeps them legible in both light and dark mode. Scoped to .eh-areas
     so it wins over main.scss without !important. */
  .eh-areas .eh-area-figure {
    margin: 0 auto 1.4rem;
    max-width: 1000px;
    background: #fff;
    border: 1px solid var(--global-divider-color);
    border-radius: 10px;
    padding: 0.6rem;
    text-align: center;
  }
  .eh-areas .eh-area-infographic {
    display: block;
    width: 100%;
    max-width: 100%;
    height: auto;
    margin: 0 auto;
    border-radius: 4px;
  }
  @media (max-width: 560px) {
    .eh-areas .eh-area-figure {
      max-width: 100%;
    }
  }

  /* Papers reuse the publications bib.liquid styling. Each paper is rendered by
     its own single-entry {% raw %}{% bibliography %}{% endraw %} call, so:
     (a) hide the left venue-abbreviation column and let the body span full
         width (same effect as the publications page), and
     (b) number entries sequentially per pillar with a CSS counter on the
         container (each entry's own <ol> would otherwise restart at 1). */
  .eh-areas .eh-area-papers {
    counter-reset: eh-paper;
  }
  .eh-areas .eh-area-papers ol.bibliography {
    margin-bottom: 0;
    list-style: none;
    padding-left: 0;
  }
  .eh-areas .eh-area-papers ol.bibliography li {
    counter-increment: eh-paper;
    margin-bottom: 1rem;
    list-style: none;
  }
  .eh-areas .eh-area-papers ol.bibliography li .abbr {
    display: none;
  }
  .eh-areas .eh-area-papers ol.bibliography li > .row > [class*="col-sm-8"],
  .eh-areas .eh-area-papers ol.bibliography li > .row > [class*="col-sm-10"] {
    flex: 0 0 100%;
    max-width: 100%;
  }
  .eh-areas .eh-area-papers ol.bibliography li .title::before {
    content: counter(eh-paper) ". ";
    font-weight: 600;
    margin-right: 0.15em;
  }
</style>

## Research Funding

<div class="eh-funding">
  <div class="eh-fund-group">
    <h3 class="eh-fund-label">Awarded / Participated</h3>
    <p class="eh-fund-role">Led full proposal development as Graduate Research Assistant (PI: Dr. Satish V. Ukkusuri), from conceptualization and writing through submission, and contributed to project execution.</p>
    <ul class="eh-fund-list">
      <li class="eh-fund-item">
        <span class="eh-fund-title">Attracting and Retaining the Transportation Workforce and At-Risk Targeted Areas</span>
        <span class="eh-fund-meta">INDOT &middot; $225,000 &middot; 2024&ndash;2026</span>
      </li>
      <li class="eh-fund-item">
        <span class="eh-fund-title">A Multi-Resolution Simulation Platform for Transportation System Security Testing and Evaluation</span>
        <span class="eh-fund-meta">USDOT University Transportation Center (TraCR) &middot; $340,000 &middot; 2024</span>
      </li>
      <li class="eh-fund-item">
        <span class="eh-fund-title">Training Gap Analysis for INDOT Workforce</span>
        <span class="eh-fund-meta">INDOT &middot; $213,500 &middot; 2023&ndash;2025</span>
      </li>
    </ul>
  </div>

  <div class="eh-fund-group">
    <h3 class="eh-fund-label">Submitted / In Preparation</h3>
    <ul class="eh-fund-list">
      <li class="eh-fund-item">
        <span class="eh-fund-title">Resilience-Based Prioritization Framework for Cooperative UAV&ndash;UGV Road Maintenance</span>
        <span class="eh-fund-meta">INDOT &middot; $200,000 &middot; Co-PI &middot; <em>proposal, under review</em></span>
      </li>
    </ul>
  </div>

  <div class="eh-fund-group">
    <h3 class="eh-fund-label">Research Support</h3>
    <ul class="eh-fund-list">
      <li class="eh-fund-item">
        <span class="eh-fund-title">Google Cloud Research Credits</span>
        <span class="eh-fund-meta">Google Cloud (computing grant) &middot; $1,000 &middot; 2025</span>
      </li>
    </ul>
  </div>
</div>

<style>
  .eh-funding { margin: 0.5rem 0 0; }
  .eh-funding .eh-fund-group { margin: 0 0 1.6rem; }
  .eh-funding .eh-fund-group:last-child { margin-bottom: 0; }
  .eh-funding .eh-fund-label {
    font-size: 1.05rem;
    font-weight: 600;
    color: var(--global-text-color);
    margin: 0 0 0.5rem;
    padding-bottom: 0.25rem;
    border-bottom: 2px solid var(--global-theme-color);
    display: inline-block;
  }
  .eh-funding .eh-fund-role {
    font-size: 0.9rem;
    color: var(--global-text-color-light);
    margin: 0 0 0.7rem;
  }
  .eh-funding .eh-fund-list { list-style: none; padding: 0; margin: 0; }
  .eh-funding .eh-fund-item {
    padding: 0 0 0 0.9rem;
    border-left: 2px solid var(--global-divider-color);
    margin: 0 0 0.8rem;
  }
  .eh-funding .eh-fund-item:last-child { margin-bottom: 0; }
  .eh-funding .eh-fund-title {
    display: block;
    color: var(--global-text-color);
    line-height: 1.45;
  }
  .eh-funding .eh-fund-meta {
    display: block;
    font-size: 0.9rem;
    color: var(--global-text-color-light);
    margin-top: 0.15rem;
  }
  .eh-funding .eh-fund-meta em {
    font-style: italic;
    color: var(--global-theme-color);
  }
</style>
