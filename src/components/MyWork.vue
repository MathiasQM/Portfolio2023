<script setup lang="ts">
import {onMounted} from 'vue'
var nlm = "/assets/NLM.png"
var Grainient = "@/assets/Grainient.png"
var PC = "/assets/PC.png"
var Synkron = "/assets/SynkronMedia.png"



onMounted(() => {
  const observer = new IntersectionObserver((entries) => {
    entries.forEach((entry) => {
        if (entry.isIntersecting) {
            entry.target.classList.add("reveal-card")
            observer.unobserve(entry.target)
        } 
    })
  },
  {
    threshold: 0.5,
  })
  document.querySelectorAll('#card').forEach((section) => {
    observer.observe(section)
  });
})
</script>

<template>
    <div class="work-container">
        <h6>My Work</h6>
        <h2>Projects made by myself and in collaboration with others</h2>
        <p>I do a lot of projects in my sparetime, both freelance work as well as my own work to keep my craving for creating at bay!</p>
        <div class="work-wrapper">
            <div class="work-card-left" id="card">
                <img :src="Grainient" alt="">
                <h3>Grainient</h3>
                <p>A Gradient editor & generator - That will become the most advanced online gradient editor on the web. Comming soon!</p>
                <
            </div>

            <div class="work-card-right" id="card">
                <img :src="Synkron" alt="">
                <h3>Synkron Media</h3>
                <p>I helped Synkron media create their digital identity through their official portfolio website!</p>
            </div>
            
            <div class="work-card-left" id="card">
                <img :src="PC" alt="">
                <h3>Performing Citizenship</h3>
                <p>A website for a research project on Amateur theatre, supported by European Research Counsil, University of Warwick & LMU.</p>
            </div>

            <div class="work-card-right" id="card">
                <img :src="nlm" alt="Picture of Next Level Media">
                <h3>Next Level Media</h3>
                <p>A collective of passionate Frontend Devs & UX designers</p>
            </div>
        </div>
    </div>
</template>

<style scoped>
.work-container {
    display: flex;
    flex-direction: column;
    align-items: center;
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
.work-card-left, .work-card-right {
    width: 70%;
    margin: 30px 0;
    cursor: pointer;
    opacity: 0;
}

.work-card-left > img, .work-card-right > img {
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

.reveal-card{
    animation: fadein 1s ease;
    opacity: 1;
}

@keyframes fadein {
    from {opacity: 0;}
    to {opacity: 1;}
}
</style>