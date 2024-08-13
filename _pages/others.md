---
layout: page
permalink: /others/
title: others
description: Throughout my academic and professional journey, I've been fortunate to receive several recognitions that have supported my growth and development. I’m happy to share some of them here.
nav: true
nav_order: 6
images:
  - image_path: /assets/img/travel/honduras.jpeg
  - image_path: /assets/img/travel/cape.jpeg
  - image_path: /assets/img/travel/cape3.png
  - image_path: /assets/img/travel/egypt.jpeg
  - image_path: /assets/img/travel/japan.png
  - image_path: /assets/img/travel/kenya.jpeg
  - image_path: /assets/img/travel/kenya2.jpeg
  - image_path:  /assets/img/travel/petra.png
  - image_path:  /assets/img/travel/turkey.png
---

<div style="display: flex;">
    <!-- Sidebar -->
    <div style="min-width: 200px; max-width: 250px; padding-right: 20px; position: sticky; top: 20px; height: 100%;">
        <h4></h4>
        <ul style="list-style-type: none; padding-left: 0;">
            <li><a href="#chess">Chess</a></li>
            <li><a href="#academic-journey">Academic Journey</a></li>
            <li><a href="#conferences">Presentations</a></li>
            <li><a href="#traveling">Traveling</a></li>
        </ul>
    </div>

    <!-- Content -->
    <div style="flex-grow: 1;">
        <h2 id="chess">Chess</h2>
        <p style="text-align: justify;">During my years as a competitive chess player, I gained invaluable experience in strategic thinking, critical decision-making, and performing under pressure. Representing El Salvador internationally strengthened my teamwork and competitive skills. Here are some highlights from those experiences.</p>

        <div class="row mt-4">
            <div class="col-sm mt-3 mt-md-0 text-center">
                {% include figure.liquid loading="eager" path="assets/img/chess_play.jpeg" title="Central American Women Chess Champion" class="img-fluid rounded z-depth-1" style="max-width: 250px;" %}
                <div class="caption mt-2">
                    <h4>Central American Women Chess Champion</h4>
                    <p>2011</p>
                </div>
            </div>
            <div class="col-sm mt-3 mt-md-0 text-center">
                {% include figure.liquid loading="eager" path="assets/img/national_chess.jpeg" title="National Women Chess Champion of El Salvador" class="img-fluid rounded z-depth-1" style="max-width: 250px;" %}
                <div class="caption mt-2">
                    <h4>National Women Chess Champion</h4>
                    <p>2010</p>
                </div>
            </div>
            <div class="col-sm mt-3 mt-md-0 text-center">
                {% include figure.liquid loading="eager" path="assets/img/chess_team.jpeg" title="Member of the National Women Chess Team" class="img-fluid rounded z-depth-1" style="max-width: 250px;" %}
                <div class="caption mt-2">
                    <h4>Member of the National Women Chess Team</h4>
                    <p>2009 - 2013</p>
                </div>
            </div>
        </div>

        <h2 id="academic-journey">Academic Journey</h2>
        <p style="text-align: justify;">Regarding my academic journey, I’m honored to have received the <strong>York Award</strong> for exceptional academic performance, the <strong>Deloitte Foundation Doctoral Fellowship</strong> for research potential, and the <strong>Chevening Scholarship</strong> from the British Government to study my master. These recognitions have played a key role in shaping and advancing my academic path.</p>

        <div class="row mt-4 justify-content-center">
            <div class="col-sm-8 text-center">
                {% include figure.liquid loading="eager" path="assets/img/york.png" title="Deloitte, York Award, and Chevening Scholarship" class="img-fluid rounded z-depth-1" style="max-width: 400px;" %}
                <div class="caption mt-2">
                    <h4>University of York</h4>
                </div>
            </div>
        </div>

        <h2 id="conferences">Presentations</h2>
        <p style="text-align: justify;">I’ve had the opportunity to present at various significant conferences and forums. In 2024, I served as a discussant at the FARS conference and presented at the Understanding the Informal Economy Forum in Santo Domingo, Dominican Republic. Earlier, in 2019, I shared my insights at the Global Knowledge Sharing Forum on Informal Economy in Turin, Italy, and the Global Youth Employment Forum in Abuja, Nigeria, focusing on the informal economy. These presentations have allowed me to engage with diverse audiences and contribute to important discussions in my field.</p>

        <div class="row mt-4">
            <div class="col-sm mt-3 mt-md-0 text-center">
                {% include figure.liquid loading="eager" path="assets/img/itcilo.jpg" title="ITCILO" class="img-fluid rounded z-depth-1" style="max-width: 250px;" %}
                <div class="caption mt-2">
                    <h4>Global Knowledge Sharing Forum</h4>
                    <p>Italy</p>
                </div>
            </div>
            <div class="col-sm mt-3 mt-md-0 text-center">
                {% include figure.liquid loading="eager" path="assets/img/nigeria2" title="Nigeria" class="img-fluid rounded z-depth-1" style="max-width: 250px;" %}
                <div class="caption mt-2">
                    <h4>Global Youth Employment Forum</h4>
                    <p>Nigeria</p>
                </div>
            </div>
            <div class="col-sm mt-3 mt-md-0 text-center">
                {% include figure.liquid loading="eager" path="assets/img/dominicana.jpeg" title="Dominicana" class="img-fluid rounded z-depth-1" style="max-width: 250px;" %}
                <div class="caption mt-2">
                    <h4>Informal Economy Forum</h4>
                    <p>Dominican Republic</p>
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
