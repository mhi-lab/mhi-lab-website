---
---

# Welcome to the Multimodal Health Intelligence (MHl) Lab!

Our group is dedicated to the interdisciplinary field of artificial intelligence and healthcare, focusing on integrating multimodal and heterogeneous medical data for precision and personalized disease diagnosis, prognosis, and treatment decision-making. Our research focus includes: 1) medical VLMs/MLLMs; 2) biomedical data generation and medical world models; 3) agentic AI systems for intelligent healthcare; 4) time-series data analysis.

{% include section.html %}

## Selected Papers

<div class="paper-carousel">

  <button class="paper-carousel-btn prev" onclick="changePaper(-1)">&#10094;</button>

  <div class="paper-carousel-track">

    <div class="paper-card active">
      <img src="{{ 'images/photo.jpg' | relative_url }}" alt="Paper image">
      <div class="paper-card-content">
        <h3>Paper Title 1</h3>
        <p>
          This is the abstract of the first selected paper. Replace this text with the real abstract.
        </p>
      </div>
    </div>

    <div class="paper-card">
      <img src="{{ 'images/photo.jpg' | relative_url }}" alt="Paper image">
      <div class="paper-card-content">
        <h3>Paper Title 2</h3>
        <p>
          This is the abstract of the second selected paper. Replace this text with the real abstract.
        </p>
      </div>
    </div>

    <div class="paper-card">
      <img src="{{ 'images/photo.jpg' | relative_url }}" alt="Paper image">
      <div class="paper-card-content">
        <h3>Paper Title 3</h3>
        <p>
          This is the abstract of the third selected paper. Replace this text with the real abstract.
        </p>
      </div>
    </div>

  </div>

  <button class="paper-carousel-btn next" onclick="changePaper(1)">&#10095;</button>

</div>

<div class="paper-carousel-dots">
  <span class="dot active" onclick="showPaper(0)"></span>
  <span class="dot" onclick="showPaper(1)"></span>
  <span class="dot" onclick="showPaper(2)"></span>
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
let currentPaper = 0;

function showPaper(index) {
  const cards = document.querySelectorAll(".paper-carousel .paper-card");
  const dots = document.querySelectorAll(".paper-carousel-dots .dot");

  if (index >= cards.length) {
    currentPaper = 0;
  } else if (index < 0) {
    currentPaper = cards.length - 1;
  } else {
    currentPaper = index;
  }

  cards.forEach(card => card.classList.remove("active"));
  dots.forEach(dot => dot.classList.remove("active"));

  cards[currentPaper].classList.add("active");
  dots[currentPaper].classList.add("active");
}

function changePaper(step) {
  showPaper(currentPaper + step);
}
</script>
