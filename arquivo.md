---
layout: default
title: arquivo
---
Aqui encontra-se uma selecção de todos os artigos publicados até hoje.

<section id="archive">
                    <h3>2015</h3>
                                    {%for post in site.posts %}
                                    {% unless post.next %}
                    <ul class="this">
                        {% else %}
                        {% capture year %}{{ post.date | date: '%Y' }}{% endcapture %}
                        {% capture nyear %}{{ post.next.date | date: '%Y' }}{% endcapture %}
                        {% if year != nyear %}
                    </ul>
                    <h3>{{ post.date | date: '%Y' }}</h3>
                    <ul class="past">
                        {% endif %}
                        {% endunless %}
                    <p><a href="{{ post.url }}">{{ post.title }}</a><time>{{ post.date | date:" - %d %b" }}</time></p>
                    {% endfor %}
                    </ul>
</section> 
