---
layout: default
title: arquivo
---
Aqui encontra-se uma selecção de todos os artigos publicados até hoje.

<section id="archive">
                    <h2>2015</h2>
                                    {%for post in site.posts %}
                                    {% unless post.next %}
                    <article class="this">
                        {% else %}
                        {% capture year %}{{ post.date | date: '%Y' }}{% endcapture %}
                        {% capture nyear %}{{ post.next.date | date: '%Y' }}{% endcapture %}
                        {% if year != nyear %}
                    </article>
                    <h2>{{ post.date | date: '%Y' }}</h2>
                    <article class="past">
                        <p>
                        {% endif %}
                        {% endunless %}
                    <strong><a href="{{ post.url }}">{{ post.title }}</a></strong>      
                    <time datetime="{{ post.date | xmlschema }}">{{ post.date | date: " - %d %b" }}</time>  
                    {% endfor %}
                </p>
                    </article>
</section> 


<div class="hfeed">
	<article class="hentry entry">
	  <p>{% for post in site.posts offset %}
          <strong><a href="{{ post.url }}">{{ post.title }}</a></strong>
	      <time datetime="{{ post.date | xmlschema }}">{{ post.date | date: " - %d-%m-%Y" }}</time>
	      
	      <br>
	  {% endfor %}
	</p>
	</article>
</div>