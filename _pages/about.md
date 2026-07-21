---
permalink: /
title: "Yinuo Liu"
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

<style>
.page__content { font-size: 0.85em; } 
</style>


Hello! I am a Data Analyst Coordinator at [Nationwide Children's Hospital](https://www.nationwidechildrens.org), working in the [Institute for Mental & Behavioral Health Research](https://www.nationwidechildrens.org/research/areas-of-research/institute-for-mental-and-behavioral-health-research) under [Dr. Eric A. Youngstrom](https://scholar.google.com/citations?user=xsHZ_3UAAAAJ&hl=en&oi=ao).

My research sits at the intersection of **data science**, **artificial intelligence**, and **clinical psychology**. I focus on three key areas:
1. **Machine Learning & Predictive Modeling.** Applying and managing machine learning, predictive analytics, and evidence-based decision tools to large-scale and electronic health record (EHR) data to improve diagnosis and measurement-based care.
2. **Artificial Intelligence in Clinical & Research Workflows.** Developing and evaluating AI-based workflows, including large language models and vision language models, to automate and scale research and clinical processes, such as meta-analysis, information evaluation, and multimedia-based clinical assessment.
3. **Clinical Mental Health and Assessment.** Combining clinical knowledge with strong quantitative skills, including regression-based norming, to build and validate assessment benchmarks across diverse data sources like clinical research samples, nationally representative datasets, and electronic health records.

I graduated from the University of North Carolina at Chapel Hill with a BS in Psychology and a BA in Computer Science (both with a 4.0 major GPA, overall GPA 3.97).

Feel free to reach me at: Yinuo.Liu@nationwidechildrens.org

## Publications

<div class="about-content">
  {% assign all_pubs = site.publications | sort: 'order' %}

  {% for post in all_pubs %}
    
    {% if post.category == "preprints" %}
      {% assign badge_class = 'badge-under-review' %}
      {% assign badge_text = 'Under Review' %}
    {% elsif post.category == "Journal Article" %}
      {% assign badge_class = 'badge-colm' %}
      {% assign badge_text = 'Peer-Reviewed' %}
    {% elsif post.category == "book-chapters" %}
      {% assign badge_class = 'badge-thesis' %}
      {% assign badge_text = 'Book Chapter' %}
    {% else %}
      {% assign badge_class = 'badge-default' %}
      {% assign badge_text = 'Peer-Reviewed' %}
    {% endif %}

    <div class="pub-item">
      <div class="pub-badge {{ badge_class }}">
        {{ badge_text }}
      </div>

      <div class="pub-content">
        {% if post.paperurl %}
        <a href="{{ post.paperurl }}" class="pub-title">{{ post.title }}</a>
        {% else %}
        <span class="pub-title">{{ post.title }}</span>
        {% endif %}
        
        <div class="pub-authors">
          {{ post.authors | default: "Authors List Placeholder" }}
        </div>
        
        <div class="pub-venue">
          {% if post.category == "preprints" %}{{ post.venue | split: " (" | first }}{% else %}{{ post.venue }}{% endif %}
        </div>

        {% if post.note %}
        <div class="pub-note">{{ post.note }}</div>
        {% endif %}
      </div>
      <div class="pub-year-bg">{{ post.date | date: "%Y" }}</div>
    </div>
  {% endfor %}
</div>

## Skills

<div class="about-content">
  <div class="skills-section">

    <div class="skill-category">
      <div class="skill-category-title">Programming Languages</div>
      <div class="skill-tags">
        <span class="skill-tag">Python</span>
        <span class="skill-tag">Java</span>
        <span class="skill-tag">C</span>
        <span class="skill-tag">JavaScript</span>
        <span class="skill-tag">HTML</span>
        <span class="skill-tag">SQL</span>
      </div>
    </div>

    <div class="skill-category">
      <div class="skill-category-title">Statistics and Questionnaire Software</div>
      <div class="skill-tags">
        <span class="skill-tag">R</span>
        <span class="skill-tag">Mplus</span>
        <span class="skill-tag">SAS</span>
        <span class="skill-tag">SPSS</span>
        <span class="skill-tag">Qualtrics</span>
        <span class="skill-tag">REDCap</span>
      </div>
    </div>

    <div class="skill-category">
      <div class="skill-category-title">Modeling and Analysis</div>
      <div class="skill-tags">
        <span class="skill-tag">Machine Learning</span>
        <span class="skill-tag">Generalized Additive Models</span>
        <span class="skill-tag">Latent Class Analysis</span>
        <span class="skill-tag">Item Response Theory</span>
      </div>
    </div>

  </div>
</div>
