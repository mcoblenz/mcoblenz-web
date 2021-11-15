---
layout: page
title: projects
permalink: /projects/
description: 
nav: true
---

#### Completed Projects

<a href="https://crates.io/crates/bronze_gc">Bronze</a> is a prototype garbage collector for Rust. The design and evaluation of Bronze are described in a <a href="https://arxiv.org/abs/2110.01098">paper</a>. In an experiment, I found that Bronze users completed a programming task that required complex aliasing in <em>a third</em> as much time as people using standard Rust (without Bronze).

<a href="http://www.obsidian-lang.com">Obsidian</a> is a new programming language for blockchain smart contracts. I developed <a href="https://dl.acm.org/doi/10.1145/3452379">user-centered design methods</a> to integrate strong static safety features while maintaining usability. The language definition, formalization, and case studies were published in <a href="https://dl.acm.org/doi/10.1145/3417516">TOPLAS</a>; an empirical evaluation was published at <a href="https://dl.acm.org/doi/10.1145/3428200">OOPSLA</a>. A 4-minute <a href="https://youtu.be/WOGupEHzef8">video</a> summarizes and demonstrates Obsidian.

<a href="http://glacier.coblenz.us">Glacier</a> is an extension to Java that supports transitive class immutability. I <a href="https://ieeexplore.ieee.org/abstract/document/7985688/">showed</a> that Glacier can be used easily by Java programmers to detect accidental mutation of immutable structures.

#### New projects

Rust's type system is generally considered to be <a href="https://www.usenix.org/conference/soups2021/presentation/fulton">hard to use</a>. Garbage collection helps in complex cases (see the Bronze project above), but what about for the simpler cases? I'm conducting an observational study of students who are taking a Rust programming class to identify approaches to make Rust easier to use and to make teaching it more effective.

APIs can be thought of as small programming languages. There's a ton of <a href="https://restfulapi.net">guidelines</a> for how to design good REST APIs, but those guidelines are not backed by emprical evidence. And some of the guidelines that exist, such as <em>write good documentation</em>, lacks good enforcement mechanisms. For example, OpenAPI is a specification format, but the specifications are vague. You can say your API takes <a href="https://spec.openapis.org/oas/v3.1.0#data-types">integers</a>, but not that the integer has to be less than 10, or that the integer has to be a valid key in some other table. Then, the documentation inevitably gets out of date. And confusing API design can lead to bugs in client programs, resulting in fragile applications. I'm interviewing designers and users of REST APIs to understand how we can make it easier to design and use REST APIS.

Spreadsheets can be error-prone. Most work on spreadsheet bugs has focused on bugs that result directly from incorrect formulas. Another source, however, is structural changes in spreadsheets, which can break formulas that reference the table that was modified. I have a plan to fix this and simultaneously make complex computations easier for spreadsheet data. I'm not quite ready to share a prototype, though…

<!-- <div class="projects grid">

  {% assign sorted_projects = site.projects | sort: "importance" %}
  {% for project in sorted_projects %}
  <div class="grid-item">
    {% if project.redirect %}
    <a href="{{ project.redirect }}" target="_blank">
    {% else %}
    <a href="{{ project.url | relative_url }}">
    {% endif %}
      <div class="card hoverable">
        {% if project.img %}
        <img src="{{ project.img | relative_url }}" alt="project thumbnail">
        {% endif %}
        <div class="card-body">
          <h2 class="card-title text-lowercase">{{ project.title }}</h2>
          <p class="card-text">{{ project.description }}</p>
          <div class="row ml-1 mr-1 p-0">
            {% if project.github %}
            <div class="github-icon">
              <div class="icon" data-toggle="tooltip" title="Code Repository">
                <a href="{{ project.github }}" target="_blank"><i class="fab fa-github gh-icon"></i></a>
              </div>
              {% if project.github_stars %}
              <span class="stars" data-toggle="tooltip" title="GitHub Stars">
                <i class="fas fa-star"></i>
                <span id="{{ project.github_stars }}-stars"></span>
              </span>
              {% endif %}
            </div>
            {% endif %}
          </div>
        </div>
      </div>
    </a>
  </div>
{% endfor %}

</div> -->
