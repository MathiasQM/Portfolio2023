<script setup>
const CV = "/assets/MathiasCV.pdf";
</script>
<template>
  <div class="header-section">
    <h1>mathias.</h1>
    <h4>
      a frontend developer with a passion for user experience, design and the
      newest technology. <br />
      <a class="download" :href="CV" download>Download CV</a>
    </h4>
  </div>
</template>

<style scoped>
.download {
  cursor: pointer;
  text-decoration: none;
  color: rgb(115, 102, 86);
  font-size: 1rem;
  padding: 10px 20px;
  transition: 500ms ease;
}

.download:hover {
  background-color: black;
  color: white;
  border-radius: 5px;
  width: 200px;
  height: 50px;
}
.header-section {
  top: 50px;
  width: 100%;
  height: 100vh;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}

h1 {
  transform: rotate(-90deg);
  font-size: 12vw;
  justify-self: center;
}

h4 {
  width: 90%;
  line-height: 50px;
  position: relative;
  text-align: center;
  bottom: -20%;
}

@media only screen and (min-width: 900px) {
  h1 {
    transform: rotate(0deg);
    font-size: 15vw;
    display: none;
  }

  h4 {
    width: 60%;
  }
}
</style>
