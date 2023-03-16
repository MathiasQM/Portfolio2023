<script setup lang="ts">
import { onMounted } from "vue";
import { Icon } from "@iconify/vue";
let ReelGenerator = "/assets/Grainient/ReelGenerator.png"
let gradientEditor = "/assets/Grainient/EditorGradientEditor.png"
let gradientLogo = "/assets/Grainient/Grainientlogo.png"
let PC = "/assets/PC.png"
let Synkron = "/assets/Sunkron.webp"


onMounted(() => {
  const observer = new IntersectionObserver(
    (entries) => {
      entries.forEach((entry) => {
        if (entry.isIntersecting) {
          entry.target.classList.add("reveal-card");
          observer.unobserve(entry.target);
        }
      });
    },
    {
      threshold: 0.5,
    }
  );
  document.querySelectorAll("#card").forEach((section) => {
    observer.observe(section);
  });
});
</script>

<template>
  <div class="work-container">
    <h6>My Work</h6>
    <h2>Projects made by myself and in collaboration with others</h2>
    <p>
      I do a lot of projects in my sparetime, both freelance work as well as my
      own work to keep my craving for creating at bay!
    </p>
  </div>

  <div class="fp">
    <div class="fp-wrapper">
      <img
        class="fp-logo"
        :src="gradientLogo"
        alt="Grainient project logo"
      />
      <p>
        A Gradient editor & generator. This is a personal project of mine, that
        will showcase my skill in UX/UI and webdevelopment. <br /><br />
        I can't share the Github Repo yet, but contact me and I'm sure we can
        figure something out!
      </p>

      <a style="color: white" href="https://grainient.mathiasqm.dk/">Grainient Demo</a>

      <div class="icons">
        <Icon width="20" icon="logos:vue" />
        <Icon width="20" icon="vscode-icons:file-type-typescript-official" />
        <Icon width="20" icon="skill-icons:tailwindcss-light" />
        <Icon width="20" icon="skill-icons:supabase-light" />
      </div>

      <!-- <div class="generator-section"> -->
        <img
          class="gradient-generator"
          :src="ReelGenerator"
          alt="Grainient Generator"
        />
        <div class="generator-text">
          <h4>The Generator</h4>
          <p>
            <br /><br />
            With the Grainient generator you will be able to generate various
            types and shapes and with colors of your choosing! <br /><br />

            With the powerfull integrated editor you'll be able to personalise a
            gradient as you please.
          </p>
        </div>
        <!-- <br /><br />
        <div class="generator-text">
          <br />
          <ul>
            <li>Copy CSS or download as jpg</li>
            <br />
            <li>Choose specific colors</li>
            <br />
            <li>Love or add to a Collection</li>
            <br />
            <li>Edit Gradient</li>
            <br />
            <li>Generate 8 types of gradients</li>
          </ul>
          <p style="font-size: 0.5rem; text-align: left;">* List might includes future features</p>
        </div> -->
      <!-- </div> -->

      <div class="editor-section">
        <div>
          <h4 style="text-align: center">The integrated editor</h4>
          <p style="color: white; text-align: center">
            <br /><br />
            With the integrated editor you'll be able to:
            <br /><br />
            <ul>
              <li style="color: white;">Move colors</li>
              <br />
              <li style="color: white;">Add animations</li>
              <br />
              <li style="color: white;">Add Noise</li>
              <br />
              <li style="color: white;">And much more...</li>
            </ul>
          </p>
        </div>
        <img
          class="gradient-editor"
          :src="gradientEditor"
          alt="Grainient Generator"
        />
      </div>
    </div>
  </div>
  <div class="other-projects">
    <div class="project-card">
      <div class="project-card-content">
        <h2>Performing Citizenship</h2>
        <div class="icons" style="position:relative; left: -2%;">
          <Icon width="20" icon="skill-icons:react-light" />
          <Icon width="20" icon="skill-icons:javascript" />
          <Icon width="20" icon="logos:css-3" />
        </div>
        <p>In collaboration with Synkron Media, we are creating Performing Citizenships digital presence. <br/> <br/>A Research Project into amateur theatre. Supported by European Research Counsil, University of Warwick & LMU.<br/> <br/> Comming Soon!</p>
        <div class="links">
          <a style="color: white; text-decoration: none;" href="https://github.com/MathiasQM/Munchenuni"><Icon width="20" color="#fff" icon="akar-icons:github-fill" /> Github</a>
          <a style="color: white; text-decoration: none;" href="/"><Icon width="20" color="#fff" icon="clarity:world-line" />Not Live</a>
        </div>
      </div>
      <div class="image">
        <img style="filter:invert(); width: 40%;" :src="PC" alt="Performing Citizenship logo">
      </div>
    </div>
    <div class="project-card">
      <div class="project-card-content">
        <h2>Synkron Media</h2>
        <div class="icons" style="position:relative;">
        <Icon width="20" icon="skill-icons:javascript" />
        <Icon width="20" icon="logos:css-3" />
        <Icon width="20" icon="logos:html-5" />
      </div>
      <p>I helped Synkron media create their digital identity through their official portfolio website!</p>

        <div class="links">
          <a style="color: white; text-decoration: none;" href="/Applications"><Icon width="20" color="#fff" icon="akar-icons:github-fill" /> Not available</a>
          <a style="color: white; text-decoration: none;" href="https://synkronmedia.com/"><Icon width="20" color="#fff" icon="clarity:world-line" />Go to Synkron Media</a>
        </div>
      </div>
      <div class="image">
        <img style="filter:invert(); width: 30%;" :src="Synkron" alt="Synkron Logo">
      </div>
    </div>
  </div>
</template>

<style scoped>

.other-projects {
  /* height: 400px; */
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  align-items: center;
  gap: 3rem;
  margin-top: 5%;
  margin-bottom: 5%;
}
.project-card {
  background-color: var(--main-black-color);
  width: 100%;
  max-width: 800px;
  min-width: none;
  display: flex;
  border-radius: 5px;
}

.project-card-content {
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  color: white;
  padding: 50px;
  min-width: 50%;
}
.project-card-content > h2 {
  color: black;
}

.image {
  display: flex;
  justify-content: center;
  align-items: center;
  overflow: hidden;
  max-width: 50%;
}
.links {
  width: 100%;
  display: flex;
  justify-content: center;
  margin-top: 10px;
  gap: 10px;
}
.links > a {
 display: flex;
 align-items: center;
 gap: 2px;
}
li {
  list-style: disc;
  text-align: left;
}
.icons {
  margin-top: 20px;
  width: 150px;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 10px;
}

.generator-section {
  margin-top: 10 0px;
  display: flex;
  justify-content: space-evenly;
}

.generator-text {
  display: flex;
  flex-direction: column;
  align-items: center;
  width: 80%;
  color: white;
  text-align: center;
}

h4 {
  color: white;
}
.fp {
  position: relative;
  display: flex;
  flex-direction: column;
  align-items: center;
  left: -10%;
  width: 120%;
  background-color: var(--main-black-color);
}

.fp-wrapper {
  margin-top: 5%;
  margin-bottom: 5%;
  width: 90%;
  display: flex;
  flex-direction: column;
  align-items: center;
}
.fp-wrapper > p {
  text-align: center;
  max-width: 400px;
  color: white;
}
.fp-logo {
  min-width: 200px;
  width: 20%;
  margin-bottom: 2.5%;
}

.gradient-generator {
  margin: 50px 0;
  width: 60%;
}

.editor-section {
  margin-top: 100px;
  width: 100%;
  display: flex;
  justify-content: space-evenly;
  align-items: center;
  flex-wrap: wrap;
  gap: 50px;
}

.editor-section h2 {
  color: black !important;
}
.gradient-editor {
  max-width: 400px;
  height: 100%;
  border-radius: 10px;
}
.work-container {
  display: flex;
  height: 400px;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  padding-top: 20px;
  text-align: center;
}
h6 {
  filter: invert();
  margin-bottom: 20px;
}

h2 {
  font-size: 2rem;
  max-width: 500px;
  filter: invert();
  margin-bottom: 20px;
}

p {
  max-width: 500px;
  line-height: 20px;
}

.work-wrapper {
  width: 100%;
  display: flex;
  flex-direction: column;
}
.work-card-left,
.work-card-right {
  width: 70%;
  margin: 30px 0;
  cursor: pointer;
  opacity: 0;
}

.work-card-left > img,
.work-card-right > img {
  width: 100%;
  max-width: 500px;
  border-radius: 5%;
}
.work-card-left {
  position: relative;
  left: 0px;
  text-align: left;
}
.work-card-right {
  display: flex;
  flex-direction: column;
  align-items: flex-end;
  align-self: flex-end;
  text-align: right;
}

.reveal-card {
  animation: fadein 1s ease;
  opacity: 1;
}

@keyframes fadein {
  from {
    opacity: 0;
  }
  to {
    opacity: 1;
  }
}

@media only screen and (max-width: 600px){
  .image {
    display: none;
  }
}
</style>
