<script setup lang="ts">
import { onMounted } from "vue";
import { Icon } from "@iconify/vue";

onMounted(() => {
  const observer = new IntersectionObserver(
    (entries) => {
      entries.forEach((entry) => {
        if (entry.isIntersecting) {
          entry.target.classList.add("reveal-text");
          observer.unobserve(entry.target);
        }
      });
    },
    {
      threshold: 0.5,
    }
  );
  document.querySelectorAll("h2").forEach((section) => {
    observer.observe(section);
  });
});
var windowWidth = window.innerWidth;
if (windowWidth > 900) {
  document.addEventListener("mousemove", function (e) {
    let circle = document.getElementById("mask")!;
    let left = e.clientX - 1200;
    let top = e.clientY - 1000;
    circle.style.left = left + "px";
    circle.style.top = top + "px";
  });
}
</script>
<template>
  <div class="worked-with">
    <h6>My skills include</h6>
    <!-- <div class="icons">
          <Icon width="30" icon="skill-icons:javascript" />
          <Icon width="30" icon="skill-icons:react-light" />
          <Icon width="30" icon="logos:vue" />
          <Icon width="30" icon="skill-icons:tailwindcss-light" />
          <Icon width="30" icon="skill-icons:supabase-light" />
          <Icon width="30" icon="vscode-icons:file-type-typescript-official" />
        </div> -->
    <span>
      <h2>Turning ideas into</h2>
    </span>
    <span>
      <h2>real life products</h2>
    </span>
    <span>
      <h2>is my passion</h2>
    </span>
    <div class="marquee-container">
      <div class="marquee">
        <div class="marquee__inner">
          <span class="rolling">ReactJS</span>
          <span class="rolling">TypeScript</span>
          <span class="rolling">VueJS</span>
          <span class="rolling">Pinia</span>
          <span class="rolling">TailwindCSS</span>
          <span class="rolling">ReactJS</span>
          <span class="rolling">TypeScript</span>
          <span class="rolling">VueJS</span>
          <span class="rolling">Pinia</span>
          <span class="rolling">TailwindCSS</span>
        </div>
      </div>
    </div>
    <div id="blur">
      <svg
        id="mask"
        xmlns="http://www.w3.org/2000/svg"
        xmlns:xlink="http://www.w3.org/1999/xlink"
        width="10in"
        height="10in"
      >
        <defs>
          <radialGradient
            id="center"
            spreadMethod="pad"
            gradientUnits="userSpaceOnUse"
            r="50%"
          >
            <stop stop-color="rgb(255,100,0)" offset="0" />
            <stop stop-color="rgba(255,0,255,0)" offset="1" />
          </radialGradient>
          <radialGradient
            id="green"
            spreadMethod="pad"
            gradientUnits="userSpaceOnUse"
            r="50%"
          >
            <stop stop-color="rgb(200,50,200)" offset="0" />
            <stop stop-color="rgb(100,0,200)" offset=".4" />
            <stop stop-color="rgba(200,0,100,0)" offset="1" />
          </radialGradient>

          <radialGradient id="left" xlink:href="#center" fx="5%" />
          <radialGradient id="left-up" xlink:href="#left" cy="50%" />

          <radialGradient id="right" xlink:href="#green" fx="95%" />
          <radialGradient id="right-up" xlink:href="#right" cy="50%" />

          <rect id="r" width="100%" height="100%" />
          <rect id="r2" width="100%" height="100%" />

          <filter id="goo">
            <feGaussianBlur
              in="SourceGraphic"
              stdDeviation="20"
              result="blur"
            />
            <feComposite in="SourceGraphic" in2="goo" operator="atop" />
          </filter>
        </defs>
        <g>
          <use id="goo1" xlink:href="#r" x="0%" y="0%" fill="url(#left-up)" />
          <use id="goo2" xlink:href="#r2" x="0%" y="0%" fill="url(#right-up)" />
        </g>
      </svg>
    </div>
  </div>
</template>

<style scoped>
.icons {
  margin-top: 20px;
  width: 150px;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 10px;
}
.worked-with {
  display: flex;
  justify-content: center;
  flex-direction: column;
  align-items: center;
  position: relative;
  left: -10%;
  width: 120%;
  height: 80vh;
  background-color: var(--main-black-color);
  overflow: hidden;
}

.worked-with > span {
  height: 40px;
  margin-bottom: 20px;
  margin: 10px;
  overflow-y: hidden;
}

h2 {
  position: relative;
  z-index: 2;
  text-align: center;
  overflow-y: hidden;
  opacity: 0;
  font-size: 200%;
}
h6 {
  position: relative;
  top: -120px;
}

.reveal-text {
  animation: reveal-text 0.5s linear;
  opacity: 1;
  padding-top: 0;
}

@keyframes reveal-text {
  0% {
    opacity: 0;
    padding-top: 10%;
  }
  100% {
    opacity: 1;
    padding-top: 0;
  }
}

.marquee-container {
  position: absolute;
  top: 80%;
  left: 50%;
  transform: translate(-50%, -50%);
  z-index: 2;
}
.rolling {
  font-family: sofia-pro, sans-serif;
  display: inline-block;
  position: relative;
  -webkit-text-stroke: 1.5px #fff;
  text-stroke: 1.5px #fff;
  -webkit-text-fill-color: transparent;
  text-fill-color: transparent;
  color: transparent;
  transition: opacity 0.4s;
  font-weight: 900;
  line-height: 1.15;
}
.marquee {
  position: relative;
  overflow: hidden;
  z-index: 1;
  --offset: 175vw;
  --move-initial: calc(-25% + var(--offset));
  --move-final: calc(-75% + var(--offset));
}

.marquee__inner {
  width: fit-content;
  display: flex;
  position: relative;
  transform: translate3d(var(--move-initial), 0, 0);
  animation: marquee 15s linear infinite;
}

.marquee span {
  font-size: 10vw;
  padding: 0 2vw;
}

.marquee .marquee__inner {
  animation-play-state: running;
}

@keyframes marquee {
  0% {
    transform: translate3d(var(--move-initial), 0, 0);
  }

  100% {
    transform: translate3d(var(--move-final), 0, 0);
  }
}

#blur {
  position: relative;
  background: transparent;
  z-index: 1;
  filter: blur(40px);
  -webkit-backdrop-filter: blur(40px);
}
svg {
  position: absolute;
  z-index: 0;
  display: block;
}

#goo1,
#goo2 {
  -webkit-backface-visibility: hidden;
  -moz-backface-visibility: hidden;
  -webkit-transform: translate3d(0, 0, 0);
  -moz-transform: translate3d(0, 0, 0);
  transform-origin: center;
}

#goo1 {
  animation: rotate 5s ease infinite alternate;
}

#goo2 {
  animation: rotate 10s ease infinite alternate-reverse;
}

@keyframes rotate {
  0% {
    transform: rotate(20deg);
  }

  50% {
    transform: rotate(60deg) scale(0.5);
  }
}

@media only screen and (min-width: 900px) {
  h2 {
    font-size: 300%;
  }

  .worked-with > span {
    height: 50px;
  }
}
</style>
