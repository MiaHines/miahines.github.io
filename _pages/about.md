---
permalink: /
title: "A Little Bit About Me"
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

I'm a third-year PhD student in the Computer Science department at Washington University in St. Louis. I'm in the [VIBE Lab](https://visualdata.wustl.edu/) and advised by Dr. Alvitta Ottley. 

I'm broadly interested in analyzing real-world social dissemination and engagement with data visualizations. In particular, I primarily evaluate visualization design patterns of public health organizations in consideration of style, accessibility, and messaging. 

I've been awarded multiple research fellowships: Clare Boothe Luce Graduate Fellowship, AI-ACCESS NRT Fellowship, and GEM Associate Fellowship. I earned a Bachelor of Arts (B.A.) degree at Grinnell College in Computer Science and a concentration in Statistics in May 2024. I have served as an undergraduate research assistant in Human-Computer Interaction, Social Computing, and Data Science at Brown University (2022) and MIT Media Lab (2023).

Data Visualization Research Interests 
======
- Public Health 
- Public Service
- Social Engagement 
- Accessibility 
- Infographics

<section class="updates-container" aria-labelledby="updates-heading">

  <h2 id="updates-heading">Updates</h2>

  <div 
    id="updates"
    aria-live="polite"
    aria-atomic="true"
  >
    {% for update in site.data.updates %}
    <article class="update {% if forloop.first %}active{% endif %}">
      <time datetime="{{ update.date }}">
        {{ update.date }}
      </time>
      <p>{{ update.text }}</p>
    </article>
    {% endfor %}
  </div>

  <button 
    id="update-toggle"
    type="button"
    aria-label="Pause updates rotation">
    Pause updates
  </button>

</section>

<script>
document.addEventListener("DOMContentLoaded", function () {

  const updates = document.querySelectorAll(".update");
  const button = document.getElementById("update-toggle");

  let current = 0;
  let paused = false;

  function showUpdate(index) {
    updates.forEach(update => {
      update.classList.remove("active");
      update.setAttribute("aria-hidden", "true");
    });

    updates[index].classList.add("active");
    updates[index].setAttribute("aria-hidden", "false");
  }

  const interval = setInterval(() => {
    if (!paused) {
      current = (current + 1) % updates.length;
      showUpdate(current);
    }
  }, 7000);

  button.addEventListener("click", function () {
    paused = !paused;

    button.textContent = paused 
      ? "Resume rotation"
      : "Pause updates";

    button.setAttribute(
      "aria-label",
      button.textContent
    );
  });

});

const reduceMotion = window.matchMedia(
  "(prefers-reduced-motion: reduce)"
).matches;

if (reduceMotion) {
  paused = true;
}

</script>