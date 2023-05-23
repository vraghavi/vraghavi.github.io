<template>
  <div style="display: block">
    <div class="blend">
      <iframe class="iframe-blend" src="https://my.spline.design/untitled-81134118f1ddec3a420d15776e076b7b/"
        frameborder="0" width="100%" height="100%"></iframe>
    </div>
    <div class="hero--header">
      <div class="arrange">
        <h5 class="intro">Hi, I am</h5>
        <h3 class="name">
          Raghavi Vannala
        </h3>
        <h5 class="my--desc">
          Full Stack Web Application Developer
        </h5>
        <div class="CTAS">
          <mainbtn bgcolor="#48AE00" textcolor="white" @click="scrollDown('projects')">My Works</mainbtn>

          <mainbtn bgcolor="#white" textcolor="black" @click="scrollDown('contactme')">Contact Me</mainbtn>
        </div>
        <br />
        <div class="social-logo-section">
          <a href="https://github.com/vraghavi" target="_blank">
            <img src="../assets/github-icon.jpg" alt="Github icon" title="Github Account" class="social-logo" /></a>
          <a href="https://www.linkedin.com/in/raghavi-v/" target="_blank">
            <img src="../assets/linkedin-logo.png" alt="Linkedin icon" title="Linkedin Account" class="social-logo"
              style="width: 21px" /></a>
        </div>
      </div>
    </div>
    <div class="threedots">
      <div tabindex="6" class="indicator indicator one" data-scrollto="hero--header"></div>
      <div tabindex="7" class="indicator two" data-scrollto="aboutme"></div>
      <div tabindex="8" class="indicator three" data-scrollto="projects"></div>
      <div tabindex="9" class="indicator four" data-scrollto="contactme"></div>
    </div>
  </div>

  <section class="aboutme">
    <aboutme></aboutme>
  </section>
  <section class="projects" id="projects">
    <h2 style="font-size: 50px; text-align: center; margin-bottom: -8px">
      Projects
    </h2>
    <h4 class="interaction-note">Interact with the demos to the left</h4>

    <!-- MAIN CAROUSEL -->

    <Carousel>
      <Slide v-for="slide in projects" :key="slide">
        <div class="carousel__item">
          <section class="carouselproject">
            <div class="iframes">
              <iframe width="1135px" height="750px" :src="slide.iframe"
                style="transform: scale(0.55) translate(-195px, -80px)" frameborder="0"></iframe>
            </div>
            <div class="carouseldesc">
              <h3 style="font-size: 33px; margin-bottom: -1px">
                {{ slide.projectname }}
              </h3>
              <h3 class="languagesused">{{ slide.tools }}</h3>
              <div class="divider2"></div>
              <h3 class="projectdesc" style="
                  width: 361px;
                  line-height: 28px;
                  font-weight: 100;
                  font-size: 20px;
                  text-align: left;
                ">
                {{ slide.desc }}
              </h3>
              <br />
              <div>
                <a :href="slide.demo" target="_blank">
                  <mainbtn bgcolor="white" textcolor="black">Demo</mainbtn>
                </a>
                <a :href="slide.github" target="_blank">
                  <mainbtn bgcolor="white" textcolor="black" style="margin-left: 20px">Github</mainbtn>
                </a>
              </div>
            </div>
          </section>
        </div>
      </Slide>
      <template #addons>
        <Pagination />
      </template>
    </Carousel>

    <!-- FOR SMALLER DISPLAYS -->

    <div class="bothprojects">
      <!-- First project -->
      <section class="project1">
        <project githuburl="https://code.vt.edu/vraghavi/coursequest"
          demourl="https://vtechworks.lib.vt.edu/bitstream/handle/10919/114974/FinalDemo_v1.mp4?sequence=2&isAllowed=y"
          iframeurl="https://vtechworks.lib.vt.edu/bitstream/handle/10919/114974/FinalDemo_v1.mp4?sequence=2&isAllowed=y"
          previewurl="coursequest.png">
          <template #projectname>CourseQuest</template>
          <template #toolsused>React.js | Java Spring | MySQL | ElasticSearch | OpenAI | Google SSO</template>
          <template #description>
            Used the React.js, Java Spring, and various external services, to create a site where university affiliated
            users can search and review courses provided by their univeristy.
          </template>
        </project>
      </section>
      <!-- Second project -->
      <section class="project2">
        <project githuburl="https://github.com/vraghavi/facedetectionapp"
          demourl="https://vraghavi.github.io/facedetectionapp/" iframeurl="https://vraghavi.github.io/facedetectionapp/"
          previewurl="facedetectionapp.png">
          <template #projectname>Face Detection App</template>
          <template #toolsused>React | Javascript | ClarifAI | Tachyons CSS</template>
          <template #description>
            A React.js App to detect Face using Clarifai face-detection model.
          </template>
        </project>
      </section>
      <!-- Third project -->
      <section class="project1">
        <project githuburl="https://github.com/vraghavi/robotfriends" demourl="https://vraghavi.github.io/robotfriends/"
          iframeurl="https://vraghavi.github.io/robotfriends/" previewurl="robotfriends.png">
          <template #projectname>Robot Friends</template>
          <template #toolsused>HTML | CSS | React | Javascript</template>
          <template #description>
            Simple React Application showcasing contacts and their details with a search feature.
          </template>
        </project>
      </section>
      <!-- FOURTH PROJECT -->
      <section class="project2">
        <project githuburl="https://github.com/vraghavi/mousai" demourl="https://timely-rabanadas-9e0625.netlify.app/"
          iframeurl="https://timely-rabanadas-9e0625.netlify.app/" previewurl="mousai.png">
          <template #projectname>MOUSAI</template>
          <template #toolsused>System Design</template>
          <template #description>
            System Design for an application called MOUSAI, a podcast hosting provider with live and recorded streaming
            and different channels.
          </template>
        </project>
      </section>
    </div>
  </section>
  <section class="contactsection">
    <contactpage></contactpage>
  </section>
</template>
<script>
import mainbtn from "../helpers/button.vue";
import contactpage from "./contactspage";
import project from "./projects";
import aboutme from "./aboutme";
// import arrowClickHandle from "../modules/handleArrowClick";
import indicatorHandle from "../modules/handleIndicators";
import "vue3-carousel/dist/carousel.css";
import { Carousel, Slide, Pagination } from "vue3-carousel";

export default {
  name: "Home",
  components: {
    mainbtn,
    project,
    contactpage,
    aboutme,
    Carousel,
    Slide,
    Pagination,
  },
  data() {
    return {
      projects: [
        {
          iframe: "https://vtechworks.lib.vt.edu/bitstream/handle/10919/114974/FinalDemo_v1.mp4?sequence=2&isAllowed=y",
          projectname: "CourseQuest",
          tools: "React.js | Java Spring | MySQL | ElasticSearch | OpenAI | Google SSO",
          desc: "Used the React.js, Java Spring, and various external services, to create a site where university affiliated users can search and review courses provided by their univeristy.",
          demo: "https://vtechworks.lib.vt.edu/bitstream/handle/10919/114974/FinalDemo_v1.mp4?sequence=2&isAllowed=y",
          github: "https://code.vt.edu/vraghavi/coursequest",
          previewurl: "",
        },
        {
          iframe: "https://vraghavi.github.io/facedetectionapp/",
          projectname: "Face Detection App",
          tools: "React | Javascript | ClarifAI | Tachyons CSS",
          desc: "A React.js App to detect Face using Clarifai face-detection model.",
          demo: "https://vraghavi.github.io/facedetectionapp/",
          github: "https://github.com/vraghavi/facedetectionapp",
          previewurl: "",
        },
        {
          iframe: "https://vraghavi.github.io/robotfriends/",
          projectname: "Robot Friends",
          tools: "HTML | CSS | React | Javascript",
          desc: "Simple React Application showcasing contacts and their details with a search feature.",
          demo: "https://vraghavi.github.io/robotfriends/",
          github: "https://github.com/vraghavi/robotfriends",
          previewurl: "",
        },
        {
          iframe: "https://timely-rabanadas-9e0625.netlify.app/",
          projectname: "MOUSAI",
          tools: "System Design",
          desc: "System Design for an application called MOUSAI, a podcast hosting provider with live and recorded streaming and different channels. ",
          demo: "https://timely-rabanadas-9e0625.netlify.app/",
          github: "https://github.com/vraghavi/mousai",
          previewurl: "",
        },
      ],
    };
  },

  methods: {
    changeIndicator(current) {
      document.querySelectorAll(".indicator").forEach((circle) => {
        circle.style.background = "rgb(160, 160, 160)";
      });
      document.querySelector("." + current).style.background = "#48AE00";
    },

    scrollDown(section) {
      document.querySelector("#" + section).scrollIntoView({
        behavior: "smooth",
      });
    },
  },

  mounted() {
    // arrowClickHandle();
    indicatorHandle.call(this);
    const tldr = document.querySelector(".aboutme--right");
    const aboutme = document.querySelector(".aboutme--left");
    let observer4 = new IntersectionObserver(
      function (e) {
        if (e[0].isIntersecting) {
          aboutme.classList.add("slide");
        }
      },
      {
        threshold: 0.1,
      }
    );

    observer4.observe(tldr);
  },
};
</script>
<style src="../styles/home.scss" lang="scss"></style>
