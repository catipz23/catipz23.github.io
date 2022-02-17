<template>
  <LandingPage />
  <Description />
  <Experience :career="data.career" />
  <Skills :skills="data.skills" />
  <Works :works="data.works" />
  <Footer />
</template>


<script>
import "@/assets/css/tailwind.css";
import LandingPage from "./components/LandingPage.vue";
import Description from "./components/Description.vue";
import Experience from "./components/Experience.vue";
import Skills from "./components/Skills.vue";
import Footer from "./components/Footer.vue";
import Works from "./components/Works.vue"
import json from "./data/data-resource.json";

export default {
  name: "App",
  components: {
    LandingPage,
    Description,
    Experience,
    Skills,
    Footer,
    Works,
  },
  data() {
    return {
      data: json,
    };
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  /* margin-top: 60px; */
}
</style>
