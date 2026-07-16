---
permalink: /
title: "A Little Bit About Me"
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

I'm a third-year PhD student in the Computer Science Department at Washington University in St. Louis. I'm in the [VIBE Lab](https://visualdata.wustl.edu/) and advised by Dr. Alvitta Ottley. 

I'm broadly interested in analyzing real-world social dissemination and engagement with data visualizations. In particular, I primarily evaluate visualization design patterns of public health organizations in consideration of style, accessibility, and messaging. 

I've been awarded multiple research fellowships: Clare Boothe Luce Graduate Fellowship, AI-ACCESS NRT Fellowship, and GEM Associate Fellowship. I earned a Bachelor of Arts (B.A.) degree at Grinnell College in Computer Science and a concentration in Statistics in May 2024. I have served as an undergraduate research assistant in Human-Computer Interaction, Social Computing, and Data Science at Brown University (2022) and MIT Media Lab (2023).

Data Visualization Research Interests 
======
- Public Health 
- Public Service
- Social Engagement 
- Accessibility 
- Infographics

<div class="updates-container">
  <h2>Updates</h2>

  <div id="updates">
    {% for update in site.data.updates %}
    <div class="update {% if forloop.first %}active{% endif %}">
      <span class="update-date">{{ update.date }}</span>
      <p>{{ update.text }}</p>
    </div>
    {% endfor %}
  </div>
</div>

<script>
  let updates = document.querySelectorAll(".update");
  let current = 0;

  setInterval(() => {
    updates[current].classList.remove("active");
    current = (current + 1) % updates.length;
    updates[current].classList.add("active");
  }, 5000);
</script>