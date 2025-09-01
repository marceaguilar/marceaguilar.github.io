---
layout: page
permalink: /tidbits
title: tidbits
description:
nav: true
nav_order: 6
images:
  - image_path: /assets/img/travel/honduras.jpeg
  - image_path: /assets/img/travel/cape.png
  - image_path: /assets/img/travel/cape3.png
  - image_path: /assets/img/travel/egypt.jpeg
  - image_path: /assets/img/travel/japan.png
  - image_path: /assets/img/travel/kenya.jpeg
  - image_path: /assets/img/travel/kenya2.JPEG
  - image_path:  /assets/img/travel/petra.png
  - image_path:  /assets/img/travel/turkey.png
  - image_path:  /assets/img/travel/hawaii.png
---

<style>
  @media (max-width: 768px) {
    .sidebar {
      display: none;
    }
    .content {
      width: 100%;
    }
  }
</style>

<div style="display: flex;">
    <!-- Sidebar -->
    <div class="sidebar" style="min-width: 200px; max-width: 250px; padding-right: 20px; position: sticky; top: 20px; height: 100%;">
        <h4></h4>
        <ul style="list-style-type: none; padding-left: 0;">
            <li><a href="#conferences">Presentations</a></li>
            <li><a href="#chess">Chess</a></li>
            <li><a href="#traveling">Traveling</a></li>
        </ul>
    </div>

    <!-- Content -->
    <div class="content" style="flex-grow: 1;">
        <h2 id="conferences">Presentations</h2>
        <p style="text-align: justify;">Here are photos from some of my presentations</p>

        <div class="row mt-4">
            <div class="col-sm mt-3 mt-md-0 text-center">
                {% include figure.liquid loading="eager" path="assets/img/itcilo.jpg" title="ITCILO" class="img-fluid rounded z-depth-1" style="max-width: 250px;" %}
                <div class="caption mt-2">
                    <h5>Global Knowledge Sharing Forum</h5>
                    <p>Italy, 2019</p>
                </div>
            </div>
            <div class="col-sm mt-3 mt-md-0 text-center">
                {% include figure.liquid loading="eager" path="assets/img/nigeria2.png" title="Nigeria" class="img-fluid rounded z-depth-1" style="max-width: 250px;" %}
                <div class="caption mt-2">
                    <h5>Global Youth Employment Forum</h5>
                    <p>Nigeria, 2019</p>
                </div>
            </div>
            <div class="col-sm mt-3 mt-md-0 text-center">
                {% include figure.liquid loading="eager" path="assets/img/dominicana.jpeg" title="Dominicana" class="img-fluid rounded z-depth-1" style="max-width: 250px;" %}
                <div class="caption mt-2">
                    <h5>Informal Economy Forum</h5>
                    <p>Dominican Republic, 2024</p>
                </div>
            </div>
        </div>
        <h2 id="chess">Chess</h2>
        <p style="text-align: justify;">I played chess professionally for about 10 years. Representing El Salvador on the international stage helped me grow as a team player and enhanced my strategic thinking. Here are a few moments from that journey.</p>

        <div class="row mt-4">
            <div class="col-sm mt-3 mt-md-0 text-center">
                {% include figure.liquid loading="eager" path="assets/img/chess_play.jpeg" title="Central American Women Chess Champion" class="img-fluid rounded z-depth-1" style="max-width: 250px;" %}
                <div class="caption mt-2">
                    <h5>Central American Women Chess Champion</h5>
                    <p>2011</p>
                </div>
            </div>
            <div class="col-sm mt-3 mt-md-0 text-center">
                {% include figure.liquid loading="eager" path="assets/img/national_chess.jpeg" title="National Women Chess Champion of El Salvador" class="img-fluid rounded z-depth-1" style="max-width: 250px;" %}
                <div class="caption mt-2">
                    <h5>National Women Chess Champion of El Salvador</h5>
                    <p>2010</p>
                </div>
            </div>
            <div class="col-sm mt-3 mt-md-0 text-center">
                {% include figure.liquid loading="eager" path="assets/img/chess_team.jpeg" title="Member of the National Women Chess Team" class="img-fluid rounded z-depth-1" style="max-width: 250px;" %}
                <div class="caption mt-2">
                    <h5>Member of the National Women Chess Team of El Salvador</h5>
                    <p>2009 - 2013</p>
                </div>
            </div>
        </div>
        <h2 id="traveling">Traveling</h2>
        <p style="text-align: justify;">Traveling is one of my greatest passions, I have visited 41 countries, and I can't stop thinking about exploring more and continuing to discover the world. Below, you'll find some of my favorite places.</p>

        <div>
            <img id="main-photo" src="{{ page.images[0].image_path }}" style="width: 85%; height: auto; margin: 0 auto; display: block;" />
            <div style="display: flex; flex-wrap: wrap; justify-content: center; gap: 5px; margin-top: 5px;">
                {% for image in page.images %}
                    <img class="photo-gallery" src="{{ image.image_path }}" style="cursor: pointer; width: 19%; height: auto;" />
                {% endfor %}
            </div>
        </div>

        <script type="text/javascript">
            document.addEventListener("DOMContentLoaded", function() {
                document.querySelectorAll("img.photo-gallery").forEach(function(img) {
                    img.addEventListener("click", function() {
                        document.getElementById("main-photo").src = this.src;
                    });
                });
            });
        </script>
    </div>
</div>
