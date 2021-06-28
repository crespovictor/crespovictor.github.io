---
title: Portfolio
permalink: "/portfolio/"
layout: portfolio
description: See what I've doing and working on!
---


<div class="row row-cols-lg-4 justify-content-left row-cols-1 row-cols-md-2">
    {% assign sorted = site.portfolio_entry | sort: 'date' | reverse %}
    {% for portfolio_entry in sorted %}
    <div class="col mb-4 d-flex">
        <div class="card ms-depth-4 flex-fill">
            <a href="{{ portfolio_entry.permalink }}">
            <img src="{{ portfolio_entry.card-image}}" class="card-img-top" alt="...">
            <div class="card-body ">
                <h5 class="card-title">{{ portfolio_entry.title }}</h5>
                <p class="card-text">{{ portfolio_entry.short_description }}</p>
            </div>
            </a>
        </div>
    </div>
    {% endfor %}
</div>
