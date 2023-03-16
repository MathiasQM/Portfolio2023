<script setup lang="ts">
import { onMounted } from "vue";

onMounted(() => {
  const observer = new IntersectionObserver(
    () => {
      document.getElementById("box")!.style.display = "flex";
    },
    {
      threshold: 0.5,
    }
  );
  var circle = document.getElementById("box")!;
  observer.observe(circle);
});

var windowWidth = window.innerWidth;
if (windowWidth > 900) {
  window.onscroll = () => {
    var pos = window.scrollY - 1000;
    document.getElementById("box")!.style.width = pos * 5 + "px";
  };
}
</script>
<template>
  <div class="footer-container">
    <div class="logo-section" style="max-width: 90%">
      <h2>I Might be a little addicted to coffee.</h2>
      <h4>Should we grab one?</h4>
    </div>
    <div id="box">
      <h6>Recommendations</h6>
      <h2 class="boxh2">I am exited to have worked with</h2>
      <a
        href="https://www.linkedin.com/in/mathias-quist-michaelsen-329590125/"
        target="_blank"
        rel="noopener noreferrer"
      >
        <div id="recommendations-container">
          <div id="recommendation-card">
            <p>
              "As a part of his studies Mathias joined our fronted team where he
              has been helping us migrate our admin system from knockout to
              vue3. Mathias doesn't shy away from a challenge and when you pair
              that with his work ethics and great personality, it makes it a
              pleasure to work with him."
            </p>
            <p>Rasmus Seeberg</p>
            <p>VP of Engineering @ iPaper</p>
          </div>
          <div id="recommendation-card hide">
            <p id="hide">
              "... Mathias was employed as a student assistant and his job was
              to retrieve and review data for our reports and surveys.
              Fortunately for iPaper, Mathias is a bit "lazy", meant in the most
              positive and cool way. So instead of just typing numbers into
              Excel, he built his own little tool that could import large
              amounts of data in a fraction of the time... <br />
              <br />Mathias has my warmest recommendations."
            </p>
            <p id="hide">Kim Lauritsen</p>
            <p id="hide">VP of Sales @ iPaper</p>
          </div>
        </div>
      </a>
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
            <use
              id="goo2"
              xlink:href="#r2"
              x="0%"
              y="0%"
              fill="url(#right-up)"
            />
          </g>
        </svg>
      </div>
    </div>
  </div>
</template>

<style scoped>
.footer-container {
  position: relative;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  left: -10%;
  width: 120%;
  height: 1000px;
  overflow: hidden;
}
.logo-section {
  height: 80vh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
.logo-container {
  max-width: 400px;
  display: flex;
  align-items: center;
  justify-content: center;
  justify-content: space-around;
  margin-bottom: 50px;
}

a {
  width: 100%;
  display: flex;
  justify-content: center;
  margin-top: 10px;
  position: relative;
  z-index: 10;
  cursor: pointer;
  text-decoration: none;
  color: black;
  font-size: 1.5rem;
}
.logo-container > img,
a > img {
  width: 45%;
  position: relative;
}

h2 {
  text-align: center;
  position: relative;
  margin-bottom: 20px;
  z-index: 10;
  filter: invert(100%);
  font-size: 2rem;
}

h4 {
  font-size: 1.5rem;
  position: relative;
  z-index: 10;
}

h3 {
  position: relative;
  z-index: 10;
  margin-top: 20px;
  font-size: 2rem;
}

#recommendations-container {
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
}

#recommendation-card {
  overflow: hidden;
  width: 400px;
  min-height: 200px;
  padding: 20px;
  border: 1px solid black;
  border-radius: 10px;
  text-align: center;
  background-color: rgba(0, 0, 0, 0.1);
  display: flex;
  flex-direction: column;
  justify-content: space-around;
}

a {
  font-size: 1rem;
}

#hide {
  display: none;
}

p {
  color: black;
  line-height: 17px;
  font-size: 1rem;
  width: 400px;
  text-align: center;
}

#box {
  max-width: 4000px;
  width: 1000px;
  position: relative;
  z-index: 9;
  display: none;
  aspect-ratio: 1 / 1;
  background-color: #fff;
  border-radius: 100%;
  filter: invert(100%);
  animation-name: fadein;
  animation-duration: 2s;
  opacity: 1;
  flex-direction: column;
  align-items: center;
  padding-top: 100px;
  overflow: hidden;
  bottom: -10%;
}

.boxh2 {
  width: 300px;
  font-size: 2rem;
}

@keyframes fadein {
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}

#blur {
  align-self: center;
  background: transparent;
  z-index: 1;
  filter: blur(40px);
  -webkit-backdrop-filter: blur(40px);
  -webkit-backdrop-filter: opacity(100%);
}

svg {
  position: relative;
  bottom: 30%;
  z-index: 0;
  display: block;
  -webkit-filter: invert(0%);
}

#goo1,
#goo2 {
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

@media only screen and (min-width: 900) {
  #hide {
    display: block;
  }
  .footer-container {
    height: 800px;
  }
  #box {
    width: 0px;
  }
  h2 {
    font-size: 2.5rem;
  }
}
</style>
