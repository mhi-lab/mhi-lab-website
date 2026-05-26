---
title: Home
nav:
  order: 1
  tooltip: Home
---

# Welcome to the Multimodal Health Intelligence (MHl) Lab!

Our group is dedicated to the interdisciplinary field of artificial intelligence and healthcare, focusing on integrating multimodal and heterogeneous medical data for precision and personalized disease diagnosis, prognosis, and treatment decision-making. Our research focus includes: 1) medical VLMs/MLLMs; 2) biomedical data generation and medical world models; 3) agentic AI systems for intelligent healthcare; 4) time-series data analysis.

{% include section.html %}

## Highlights

<div class="pub-carousel">

  <button class="pub-arrow pub-prev" type="button" onclick="changePub(-1)">
    &#10094;
  </button>

  <div class="pub-slides">

    <div class="pub-slide is-active">
      <img src="{{ 'images/publications/ma-sam.png' | relative_url }}" alt="MA-SAM paper image">
      <div class="pub-content">
        <h3>MA-SAM: Modality-agnostic SAM Adaptation for 3D Medical Image Segmentation</h3>
        <p>
          <strong>Authors:</strong> Cheng Chen, Juzheng Miao, Dufan Wu, Zhiling Yan, Sekeun Kim, Jiang Hu, Aoxiao Zhong, Zhengliang Liu, Lichao Sun, Xiang Li, Tianming Liu, Pheng-Ann Heng, Quanzheng Li
        </p>
        <p>
          <strong>Venue:</strong> Medical Image Analysis (MedIA), 2024
        </p>
        <a class="pub-link" href="https://www.sciencedirect.com/science/article/pii/S1361841524002354" target="_blank" rel="noopener noreferrer">
          View Paper
        </a>
      </div>
    </div>

    <div class="pub-slide">
      <img src="{{ 'images/publications/synermedgen.png' | relative_url }}" alt="SynerMedGen paper image">
      <div class="pub-content">
        <h3>SynerMedGen: Synergizing Medical Multimodal Understanding with Generation via Task Alignment</h3>
        <p>
          <strong>Authors:</strong> Weiren Zhao, Yi Dong, Cheng Chen
        </p>
        <p>
          <strong>Venue:</strong> ICML, 2026
        </p>
        <a class="pub-link" href="https://arxiv.org/abs/2605.08724" target="_blank" rel="noopener noreferrer">
          View Paper
        </a>
      </div>
    </div>

    <div class="pub-slide">
      <img src="{{ 'images/publications/cogegcd.png' | relative_url }}" alt="Compositional Perception and Generalizing Induction paper image">
      <div class="pub-content">
        <h3>Compositional Perception and Generalizing Induction: Latent Compositional Manifold Assumption on Generalized Category Discovery</h3>
        <p>
          <strong>Authors:</strong> Luyao Tang, Jiewei Zheng, Kunze Huang, Chaoqi Chen, Yue Huang, Cheng Chen
        </p>
        <p>
          <strong>Venue:</strong> ICML, 2026
        </p>
        <a class="pub-link" href="#" onclick="return false;">
          View Paper
        </a>
      </div>
    </div>

    <div class="pub-slide">
      <img src="{{ 'images/publications/bures-isotropy-alignment.png' | relative_url }}" alt="Bures-Isotropy Alignment paper image">
      <div class="pub-content">
        <h3>Bures-Isotropy Alignment: Manifold Learning of Generalized Category Discovery</h3>
        <p>
          <strong>Authors:</strong> Luyao Tang, Kunze Huang, Chaoqi Chen, Cheng Chen
        </p>
        <p>
          <strong>Venue:</strong> ICLR, 2026
        </p>
        <a class="pub-link" href="https://openreview.net/forum?id=nfVKTJ1MJ3" target="_blank" rel="noopener noreferrer">
          View Paper
        </a>
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
  <button class="pub-dot" type="button" onclick="showPub(3)"></button>
</div>

{%
  include button.html
  link="publication"
  text="See our publications"
  icon="fa-solid fa-arrow-right"
  flip=true
  style="bare"
%}

<script>
let currentPub = 0;
let pubTimer = null;

function showPub(index) {
  const slides = document.querySelectorAll(".pub-slide");
  const dots = document.querySelectorAll(".pub-dot");

  if (!slides.length) return;

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
  resetPubTimer();
}

function startPubTimer() {
  pubTimer = setInterval(function () {
    showPub(currentPub + 1);
  }, 8000);
}

function resetPubTimer() {
  if (pubTimer) {
    clearInterval(pubTimer);
  }
  startPubTimer();
}

startPubTimer();
</script>
