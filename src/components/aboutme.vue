<template>
  <div class="aboutme--left">
    <h2 class="aboutmetext">About Me</h2>
    <h4 class="aboutmedesc">
      Hi! I'm Raghavi Vannala, a highly skilled software developer with a Masters in Computer Science and Applications
      from Virginia Polytechnic Institute and State University. With expertise in Java, TypeScript, Javascript and
      frameworks like Angular and React.js, I have delivered impactful projects, including dynamic web applications for
      electric vehicles and migration of legacy systems using modern tech stacks.
    </h4>
  </div>
  <div class="divider-div">
    <div class="divider"></div>
  </div>
  <div class="aboutme--right">
    <h2 style="font-size: 39px">TL;DR</h2>
    <h4 class="tldr">Name: Raghavi Vannala</h4>
    <h4 class="tldr">Education: Masters in Computer Science and Applications</h4>
    <h4 class="tldr">Skills: React.js | Angular | JS | Spring Java | AWS</h4>
    <h4 class="tldr">Interests: Full Stack Development, Front End Development, Back End Development</h4>
    <br />
    <a href="https://www.linkedin.com/in/raghavi-v/" target="_blank">
      <mainbtn bgcolor="linear-gradient(136deg, #2F7100, #48AE00)" textcolor="white">LinkedIn Profile</mainbtn>
    </a>
  </div>
</template>

<script>
import mainbtn from "../helpers/button.vue";

export default {
  components: { mainbtn },
};
</script>
