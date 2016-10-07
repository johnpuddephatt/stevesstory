---
title: Events
layout: post
---

<div class="row">
    {% for event in site.events %}
        <article class="{% cycle '6u', '6u$' %} 12u(small)">
          <a class="image fit thumb" href="{{ event.url }}">
            <img src="{{ event.image }}" alt="">
          </a>
            <header>
              <h4 class="date">                
                {% assign d = event.date | date: "%-d"  %}
                {% case d %}
                  {% when '1' or '21' or '31' %}{{ d }}st
                  {% when '2' or '22' %}{{ d }}nd
                  {% when '3' or '23' %}{{ d }}rd
                  {% else %}{{ d }}th
                  {% endcase %}
                {{ event.date | date: "%b" }}
                {{ event.date | date: "%Y" }}
              </h4>
                <h2><a href="{{ event.url }}">{{ event.title }}</a></h2>
            </header>
            <section>
                {{ event.excerpt }}
            </section>
            <footer>
                <ul class="actions">
                    <li><a href="{{ event.url }}" class="button">Read More</a></li>
                </ul>
            </footer>
        </article>

    {% endfor %}
</div>