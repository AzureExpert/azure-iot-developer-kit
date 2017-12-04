---
layout: splash
permalink: /
title: "An all-in-one IoT kit built for the cloud"
header:
  overlay_color: "#003c5c"
  image_path: /assets/images/landingpage-banner1.png
  call_to_action:
    - label: "Get a Kit"
      url: "https://aka.ms/iot-devkit-purchase"
      btn_class: "landing-page-btn landing-page-btn-blue"
    - label: "Project Catalog"
      url: "/docs/projects"
      btn_class: "landing-page-btn landing-page-btn-clear"
  call_to_action_secondary:
      label: "Can't wait? Play with simulator first"
      url: "https://aka.ms/iot-devkit-simulator"
  extra_logo:
    - image_path: /assets/images/logo-azure-certified.svg
      url: "https://catalog.azureiotsuite.com/details?title=MXChip-IoT-DevKit&source=home-page"
  align: center
excerpt: "All the sensors and parts you love, no soldering needed. Welcome to cloud IoT development."
part1:
  class: "light-gray"
  content:
    - title: "Essential modules and sensors on the board save your time and money"
      excerpt: "Wifi, OLED display, headphone, microphone, sensors like temperature, humidity, motion, pressure, you will love how much time and money you save to build your best IoT project."
      url: "/docs/get-started"
      btn_label: "Learn more about IoT DevKit hardware spec"
      image_path: /assets/images/landingpage-banner2.png
      attach: 
        words: "This eliminates the need to have electronics knowledge and the need to do any wiring or soldering in order to get started prototyping IoT solutions."
        author:
          photo: /assets/images/user.png
          name: Chris Pietschmann
          title: BuildAzure.com
part2:
  content:
    - title: "Visual Studio Code streamlines your development experiences"
      excerpt: "Visual Studio Code is lightweight and your goto editor of choice. It is your all-in-one tool from coding the first line to deploying to the cloud."
      url: "/docs/projects"
      btn_label: "Learn more about the one-click installation"
      image_path: /assets/images/landingpage-banner3.png
      attach: 
        words: "The sample code included scripts taking advantage of Visual Studio Code’s built-in terminal, so I didn’t have to leave my IDE to use the Azure Portal."
        author:
          photo: /assets/images/user.png
          name: Simon Bisson
          title: InfoWorld
part3:
  class: "light-gray"
  content:
    - title: "Cloud empowers your IoT solutions to next level"
      excerpt: "Code your IoT solution in the cloud! Using Azure services like IoT Hub, Stream Analytics, Machine Learning to build the best IoT solutions."
      url: "http://www.mxchip.com/az3166"
      btn_label: "Learn more about projects using Azure services"
      image_path: /assets/images/landingpage-banner4.png
      attach: 
        words: "Customer testimonal starts from here. A customer says this is pretty awesome"
        author:
          photo: /assets/images/user.png
          name: John Doe
          title: Director of Software at Contoso
projects: "0, 4, 6"
---

{% include feature_row id="part1" type="right" %}

{% include feature_row id="part2" type="left" %}

{% include feature_row id="part3" type="right" %}

<div class="feature__wrapper">
  <div class="landing-page-project">
    <h2>Highlighted Projects</h2>
    <div class="landing-page-projects">
    
      {% assign projects = page.projects | split: "," %}

      {% for projectStr in projects %}
        {% assign projectNum = projectStr | plus: 0 %}
        {% assign post = site.projects[projectNum] %}
        {% include archive-single.html type="grid" %}
      {% endfor %}

    </div>
    <a href="{{ '/docs/projects' | absolute_url }}">View our Project Catalog to learn and build more IoT solutions</a>
  </div>
</div>

<div class="light-gray">

  <div class="feature__wrapper">
    <div class="landing-page-final-item">
      <p class="landing-page-final-body">Build your own IoT application with Azure and Visual Studio Code helped today.</p>
      <a class="landing-page-final-teaser landing-page-btn landing-page-btn-blue btn--large" href="https://aka.ms/iot-devkit-purchase">Get a Kit</a>
    </div>
  </div>

</div>
