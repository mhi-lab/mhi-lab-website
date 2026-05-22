---
---

# Welcome to the Multimodal Health Intelligence (MHl) Lab!

Our group is dedicated to the interdisciplinary field of artificial intelligence and healthcare, focusing on integrating multimodal and heterogeneous medical data for precision and personalized disease diagnosis, prognosis, and treatment decision-making. Our research focus includes: 1) medical VLMs/MLLMs; 2) biomedical data generation and medical world models; 3) agentic AI systems for intelligent healthcare; 4) time-series data analysis.

{% include section.html %}

## Selected Papers

<div class="pub-carousel">

  <button class="pub-arrow pub-prev" type="button" onclick="changePub(-1)">
    &#10094;
  </button>

  <div class="pub-slides">

    <div class="pub-slide is-active">
      <img src="{{ 'images/photo.jpg' | relative_url }}" alt="Paper image">
      <div class="pub-content">
        <h3>Paper Title 1</h3>
        <p>
          This is the abstract of the first selected paper. Replace this text with the real abstract.
        </p>
      </div>
    </div>

    <div class="pub-slide">
      <img src="{{ 'images/photo.jpg' | relative_url }}" alt="Paper image">
      <div class="pub-content">
        <h3>Paper Title 2</h3>
        <p>
          This is the abstract of the second selected paper. Replace this text with the real abstract.
        </p>
      </div>
    </div>

    <div class="pub-slide">
      <img src="{{ 'images/photo.jpg' | relative_url }}" alt="Paper image">
      <div class="pub-content">
        <h3>Paper Title 3</h3>
        <p>
          This is the abstract of the third selected paper. Replace this text with the real abstract.
        </p>
      </div>
    </div>

  </div>

  <button class="pub-arrow pub-next" type="button" onclick="changePub(1)">
    &#10095;
  </button>

</div>

<div class="pub-dots">
  <button class="pub-dot is-active" type="button" onclick="showPub(0)"></button>
  <button class="pub-dot" type="button" onclick="showPub(1)"></button>
  <button class="pub-dot" type="button" onclick="showPub(2)"></button>
</div>

{%
  include button.html
  link="research"
  text="See our publications"
  icon="fa-solid fa-arrow-right"
  flip=true
  style="bare"
%}

<script>
let currentPub = 0;

function showPub(index) {
  const slides = document.querySelectorAll(".pub-slide");
  const dots = document.querySelectorAll(".pub-dot");

  if (index < 0) {
    currentPub = slides.length - 1;
  } else if (index >= slides.length) {
    currentPub = 0;
  } else {
    currentPub = index;
  }

  slides.forEach(slide => slide.classList.remove("is-active"));
  dots.forEach(dot => dot.classList.remove("is-active"));

  slides[currentPub].classList.add("is-active");
  dots[currentPub].classList.add("is-active");
}

function changePub(step) {
  showPub(currentPub + step);
}
</script>
