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


Hello! I am a Clinical Research Coordinator at [Nationwide Children's Hospital](https://www.nationwidechildrens.org), working in the [Institute for Mental & Behavioral Health Research](https://www.nationwidechildrens.org/research/areas-of-research/institute-for-mental-and-behavioral-health-research) under [Dr. Eric A. Youngstrom](https://psychiatry.unc.edu/profile/youngstrom/).

My research sits at the intersection of **clinical psychology**, **artificial intelligence**, and **psychometrics**. I focus on three key areas:
1. **AI in Clinical Research.** Developing and evaluating LLM-based workflows for abstract evaluation, CV screening, and AI-assisted meta-analysis pipelines in behavioral health research.
2. **Machine Learning in Healthcare.** Applying and comparing machine learning and evidence-based decision methods (e.g., Bayesian nomograms) to improve pediatric diagnosis and measurement-based care.
3. **Psychometrics and Scale Development.** Creating national norms and psychometric benchmarks for clinical measures related to puberty, depression, mania, quality of life, and related domains.

I graduated from the University of North Carolina at Chapel Hill with a BS in Psychology and a BA in Computer Science (both with a 4.0 major GPA, overall GPA 3.97).

Feel free to reach me at: Yinuo.Liu [at] nationwidechildrens [dot] org

## News

<div class="about-content">
  <div class="news-box"> 

    <div class="news-item">
      <div class="news-date">Apr 2026</div>
      <div class="news-content">
        Published paper in <strong>Frontiers in Research Metrics and Analytics</strong>: <i>Evaluating large language models for abstract evaluation tasks: An empirical study</i>.
      </div>
    </div>

    <div class="news-item">
      <div class="news-date">Apr 2026</div>
      <div class="news-content">
        Invited CE seminar at Nationwide Children's Hospital: <i>AI and Clinical Science in Mental and Behavioral Health: From Evidence Pipeline to Patient Outcomes</i>.
      </div>
    </div>

    <div class="news-item">
      <div class="news-date">Jan 2026</div>
      <div class="news-content">
        Poster presentation at <strong>American College of Neuropsychopharmacology</strong>, Nassau, Bahamas: <i>Advancing detection and measurement-based care of mood problems in youth</i>.
      </div>
    </div>

    <div class="news-item">
      <div class="news-date">Nov 2025</div>
      <div class="news-content">
        Three poster presentations at <strong>ABCT 2025 Annual Convention</strong>, New Orleans, LA — including Diagnostic Accuracy of Child Mania Rating Scale and quality of life in youth.
      </div>
    </div>

    <div class="news-item">
      <div class="news-date">Nov 2025</div>
      <div class="news-content">
        Selected speaker at <strong>Abigail Wexner Research Institute Annual Research Retreat</strong>: <i>Building ChatGPT-Based Abstract Scoring: Pilot and Application</i>.
      </div>
    </div>

    <div class="news-item">
      <div class="news-date">Oct 2025</div>
      <div class="news-content">
        Two poster presentations at <strong>AACAP 2025 Annual Convention</strong>, Chicago, IL — on machine learning for ODD prediction and psychosis assessment coverage.
      </div>
    </div>

    <div class="news-item">
      <div class="news-date">Jun 2025</div>
      <div class="news-content">
        Invited talk at Nationwide Children's Hospital: <i>ChatGPT 101: From Theory to Practice</i>.
      </div>
    </div>

    <div class="news-item">
      <div class="news-date">Feb 2025</div>
      <div class="news-content">
        Joined Nationwide Children's Hospital as a Clinical Research Coordinator at the Institute for Mental & Behavioral Health Research.
      </div>
    </div>

  </div> </div>


## Publications

<div class="about-content">
  {% assign manuscripts = site.publications | where: "category", "manuscripts" | sort: 'date' | reverse %}
  {% assign preprints   = site.publications | where: "category", "preprints"   | sort: 'date' | reverse %}
  {% assign book_chaps  = site.publications | where: "category", "book-chapters" | sort: 'date' | reverse %}
  {% assign all_pubs = manuscripts | concat: book_chaps | concat: preprints %}

  {% for post in all_pubs %}
    
    {% if post.category == "preprints" %}
      {% assign badge_class = 'badge-under-review' %}
      {% assign badge_text = 'Under Review' %}
    {% else %}
      {% assign venue_down = post.venue_nickname | downcase %}
      {% if venue_down contains 'frontiers' %}
        {% assign badge_class = 'badge-colm' %}
        {% assign badge_text = 'Frontiers' %}
      {% elsif venue_down contains 'book' %}
        {% assign badge_class = 'badge-thesis' %}
        {% assign badge_text = 'Book Chapter' %}
      {% else %}
        {% assign badge_class = 'badge-default' %}
        {% assign badge_text = 'Paper' %}
      {% endif %}
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
      </div>
      <div class="pub-year-bg">{{ post.date | date: "%Y" }}</div>
    </div>
  {% endfor %}
</div>
