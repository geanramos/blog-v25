---
layout: default
title: "Tags"
permalink: /tags/
body_class: tags-page
---

{% include header-home.html %}

<main class="container">
    <header class="page-header">
        <h1 class="page-title">Todas as Tags</h1>
    </header>

    <div class="tag-cloud">
        {% for tag in site.tags | sort %}
            <a href="#{{ tag[0] | slugify }}" class="tag-button">
                {{ tag[0] }} <span>({{ tag[1].size }})</span>
            </a>
        {% endfor %}
    </div>

    <div class="tags-list">
        {% for tag in site.tags | sort %}
            <section id="{{ tag[0] | slugify }}" class="tag-section">
                <h2 class="tag-section-title">{{ tag[0] }}</h2>
                {% for post in tag[1] %}
                    {% include cartao-artigo.html %}
                {% endfor %}
            </section>
        {% endfor %}
    </div>
</main>

{% include footer.html %}
