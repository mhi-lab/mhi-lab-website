---
title: Team
nav:
  order: 2
  tooltip: About our team
---

<div class="team-page">

<h2>Group Photos</h2>

<div class="team-photo-carousel" aria-label="Group photos">
  <div class="team-photo-slides">

    <figure class="team-photo-slide is-active">
      <img
        src="{{ '/images/group/group-photo-1.jpg' | relative_url }}"
        alt="MHI Lab group photo"
      >
    </figure>

    <figure class="team-photo-slide">
      <img
        src="{{ '/images/group/group-photo-2.jpg' | relative_url }}"
        alt="MHI Lab group photo"
        loading="lazy"
      >
    </figure>

    <figure class="team-photo-slide">
      <img
        src="{{ '/images/group/group-photo-3.jpg' | relative_url }}"
        alt="MHI Lab group photo"
        loading="lazy"
      >
    </figure>

  </div>

  <button
    class="team-photo-arrow team-photo-prev"
    type="button"
    aria-label="Previous photo"
  >
    &#10094;
  </button>

  <button
    class="team-photo-arrow team-photo-next"
    type="button"
    aria-label="Next photo"
  >
    &#10095;
  </button>

  <div class="team-photo-dots" aria-label="Choose a photo"></div>
</div>

<h2>Principal Investigator</h2>

{% include list.html data="members" component="portrait" filter="role == 'principal-investigator'" %}

<h2>PhD Students</h2>

{% include list.html data="members" component="portrait" filter="role == 'phd'" sort="team_order" %}

<h2>RA & Intern</h2>

{% include list.html data="members" component="portrait" filter="role == 'ra' or role == 'intern'" sort="team_order" %}

</div>

<script>
document.addEventListener("DOMContentLoaded", function () {
  const carousel = document.querySelector(".team-photo-carousel");

  if (!carousel) {
    return;
  }

  const slides = Array.from(
    carousel.querySelectorAll(".team-photo-slide")
  );

  const previousButton = carousel.querySelector(".team-photo-prev");
  const nextButton = carousel.querySelector(".team-photo-next");
  const dotsContainer = carousel.querySelector(".team-photo-dots");

  let currentSlide = 0;
  let autoplayTimer;

  function showSlide(index) {
    currentSlide = (index + slides.length) % slides.length;

    slides.forEach(function (slide, slideIndex) {
      slide.classList.toggle(
        "is-active",
        slideIndex === currentSlide
      );
    });

    const dots = dotsContainer.querySelectorAll(".team-photo-dot");

    dots.forEach(function (dot, dotIndex) {
      dot.classList.toggle(
        "is-active",
        dotIndex === currentSlide
      );

      dot.setAttribute(
        "aria-current",
        dotIndex === currentSlide ? "true" : "false"
      );
    });
  }

  function showPreviousSlide() {
    showSlide(currentSlide - 1);
  }

  function showNextSlide() {
    showSlide(currentSlide + 1);
  }

  function stopAutoplay() {
    window.clearInterval(autoplayTimer);
  }

  function startAutoplay() {
    stopAutoplay();

    if (slides.length > 1) {
      autoplayTimer = window.setInterval(
        showNextSlide,
        5000
      );
    }
  }

  slides.forEach(function (slide, index) {
    const dot = document.createElement("button");

    dot.className = "team-photo-dot";
    dot.type = "button";
    dot.setAttribute("aria-label", "Show photo " + (index + 1));

    dot.addEventListener("click", function () {
      showSlide(index);
      startAutoplay();
    });

    dotsContainer.appendChild(dot);
  });

  previousButton.addEventListener("click", function () {
    showPreviousSlide();
    startAutoplay();
  });

  nextButton.addEventListener("click", function () {
    showNextSlide();
    startAutoplay();
  });

  carousel.addEventListener("mouseenter", stopAutoplay);
  carousel.addEventListener("mouseleave", startAutoplay);
  carousel.addEventListener("focusin", stopAutoplay);

  carousel.addEventListener("focusout", function (event) {
    if (!carousel.contains(event.relatedTarget)) {
      startAutoplay();
    }
  });

  if (slides.length <= 1) {
    previousButton.hidden = true;
    nextButton.hidden = true;
    dotsContainer.hidden = true;
  }

  showSlide(0);
  startAutoplay();
});
</script>
