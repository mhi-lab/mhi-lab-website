---
title: Team
nav:
  order: 2
  tooltip: About our team
---

<div class="team-page">

<h2>Group Photos</h2>

<div class="team-photo-carousel">

  <div class="team-photo-slides">

    <figure class="team-photo-slide is-active">
      <img
        src="{{ 'images/group/group-photo-1.jpg' | relative_url }}"
        alt="MHI Lab group photo"
      >
      <figcaption>MHI Lab Group Photo, 2026</figcaption>
    </figure>

    <figure class="team-photo-slide">
      <img
        src="{{ 'images/group/group-photo-2.jpg' | relative_url }}"
        alt="MHI Lab group activity"
      >
      <figcaption>MHI Lab Group Activity, 2026</figcaption>
    </figure>

    <figure class="team-photo-slide">
      <img
        src="{{ 'images/group/group-photo-3.jpg' | relative_url }}"
        alt="MHI Lab group gathering"
      >
      <figcaption>MHI Lab Group Gathering, 2026</figcaption>
    </figure>

  </div>

  <button
    class="team-photo-arrow team-photo-prev"
    type="button"
    aria-label="Previous group photo"
  >
    &#10094;
  </button>

  <button
    class="team-photo-arrow team-photo-next"
    type="button"
    aria-label="Next group photo"
  >
    &#10095;
  </button>

  <div class="team-photo-dots" aria-label="Choose group photo"></div>

</div>

<h2>Principal Investigator</h2>

{% include list.html data="members" component="portrait" filter="role == 'principal-investigator'" %}

<h2>PhD Students</h2>

{% include list.html data="members" component="portrait" filter="role == 'phd'" sort="team_order" %}

<h2>RA & Intern</h2>

{% include list.html data="members" component="portrait" filter="role == 'ra' or role == 'intern'" sort="team_order" %}

</div>

<script>
(function () {
  const carousel = document.querySelector(".team-photo-carousel");

  if (!carousel) return;

  const slides = carousel.querySelectorAll(".team-photo-slide");
  const dotsContainer = carousel.querySelector(".team-photo-dots");
  const previousButton = carousel.querySelector(".team-photo-prev");
  const nextButton = carousel.querySelector(".team-photo-next");

  let currentPhoto = 0;
  let teamPhotoTimer = null;

  function showTeamPhoto(index) {
    if (index < 0) {
      currentPhoto = slides.length - 1;
    } else if (index >= slides.length) {
      currentPhoto = 0;
    } else {
      currentPhoto = index;
    }

    slides.forEach(function (slide, slideIndex) {
      const isActive = slideIndex === currentPhoto;

      slide.classList.toggle("is-active", isActive);
      slide.setAttribute("aria-hidden", String(!isActive));
    });

    const dots = dotsContainer.querySelectorAll(".team-photo-dot");

    dots.forEach(function (dot, dotIndex) {
      const isActive = dotIndex === currentPhoto;

      dot.classList.toggle("is-active", isActive);
      dot.setAttribute("aria-current", String(isActive));
    });
  }

  function stopTeamPhotoTimer() {
    if (teamPhotoTimer) {
      clearInterval(teamPhotoTimer);
      teamPhotoTimer = null;
    }
  }

  function startTeamPhotoTimer() {
    stopTeamPhotoTimer();

    teamPhotoTimer = setInterval(function () {
      showTeamPhoto(currentPhoto + 1);
    }, 7000);
  }

  slides.forEach(function (_, index) {
    const dot = document.createElement("button");

    dot.className = "team-photo-dot";
    dot.type = "button";
    dot.setAttribute("aria-label", "Show group photo " + (index + 1));

    dot.addEventListener("click", function () {
      showTeamPhoto(index);
      startTeamPhotoTimer();
    });

    dotsContainer.appendChild(dot);
  });

  previousButton.addEventListener("click", function () {
    showTeamPhoto(currentPhoto - 1);
    startTeamPhotoTimer();
  });

  nextButton.addEventListener("click", function () {
    showTeamPhoto(currentPhoto + 1);
    startTeamPhotoTimer();
  });

  carousel.addEventListener("mouseenter", stopTeamPhotoTimer);
  carousel.addEventListener("mouseleave", startTeamPhotoTimer);
  carousel.addEventListener("focusin", stopTeamPhotoTimer);
  carousel.addEventListener("focusout", startTeamPhotoTimer);

  showTeamPhoto(0);
  startTeamPhotoTimer();
})();
</script>

