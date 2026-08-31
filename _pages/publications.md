---
layout: page
permalink: /publications/
title: Publications
description: Peer-reviewed journal articles, conference proceedings, book chapters, technical reports, and patents. Manuscripts under review are listed first.
nav: true
nav_order: 3
---

<div class="pub-profile-links">
  <a href="https://scholar.google.com/citations?user=6--Tei4AAAAJ&hl=en" target="_blank" rel="noopener" title="Google Scholar" aria-label="Google Scholar"><i class="ai ai-google-scholar"></i> Google Scholar</a>
  <a href="https://orcid.org/0000-0003-0954-8075" target="_blank" rel="noopener" title="ORCID" aria-label="ORCID"><i class="ai ai-orcid"></i> ORCID</a>
</div>

<div class="publications">

<h2 class="bibliography-section-heading">Under Review</h2>
{% bibliography --query @article[status=underreview] %}

<h2 class="bibliography-section-heading">Journal Articles</h2>
{% bibliography --query @article[status!=underreview] %}

<h2 class="bibliography-section-heading">Conference Proceedings</h2>
{% bibliography --query @inproceedings %}

<h2 class="bibliography-section-heading">Books and Technical Reports</h2>
{% bibliography --query @incollection,@techreport %}

<h2 class="bibliography-section-heading">Patents</h2>
{% bibliography --query @misc %}

</div>
