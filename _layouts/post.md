---
layout: default
---

<!-- Page Header -->
{% if page.background %}
<header class="masthead" style="background-image: url('{{ page.background | prepend: site.baseurl | replace: '//', '/' }}')">
  {% else %}
  <header class="masthead">
    {% endif %}
    <div class="overlay"></div>
    <div class="container">
      <div class="row">
        <div class="col-lg-8 col-md-10 mx-auto">
          <div class="post-heading">
            <h1>{{ page.title }}</h1>
            {% if page.subtitle %}
            <h2 class="subheading">{{ page.subtitle }}</h2>
            {% endif %}
            <span class="meta">Posted by
              <a href="#">{% if page.author %}{{ page.author }}{% else %}{{ site.author }}{% endif %}</a>
              on {{ page.date | date: '%B %d, %Y' }}
            </span>
            {% if page.categories %}
            <br/><span class="meta">
              <i class="fa fa-list-alt" aria-hidden="true"></i>
                {% for c in page.categories %}
                  <span><a href="{{ site.baseurl }}/categories/#{{ c }}">{{ c }}</a></span>
                {% endfor %}
            </span><br/>
            {% endif %}
            {% if page.tags %}
            <span class="meta">
              <i class="fa fa-tag" aria-hidden="true"></i>
              {% for t in page.tags %}
                <span><a href="{{ site.baseurl }}/tags/#{{ t }}">{{ t }}</a></span>
              {% endfor %}
            </span>
            {% endif %}
          </div>
        </div>
      </div>
    </div>
  </header>

  <div class="container">
    <div class="row">
      <div class="col-lg-8 col-md-10 mx-auto">
        {{ content }}
        <hr>
        <div class="clearfix">
          {% if page.previous.url %}
          <a class="btn btn-primary float-left" href="{{ page.previous.url | prepend: site.baseurl | replace: '//', '/' }}" data-toggle="tooltip" data-placement="top" title="{{ page.previous.title }}">&larr; Previous<span class="d-none d-md-inline">
              Post</span></a>
          {% endif %}
          {% if page.next.url %}
          <a class="btn btn-primary float-right" href="{{ page.next.url | prepend: site.baseurl | replace: '//', '/' }}" data-toggle="tooltip" data-placement="top" title="{{ page.next.title }}">Next<span class="d-none d-md-inline">
              Post</span> &rarr;</a>
          {% endif %}
        </div>
      </div>
    </div>
  </div>