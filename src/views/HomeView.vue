<script setup lang="ts">
import HeaderSection from '@/components/HeaderSection.vue';
import WorkedWIthVue from '@/components/WorkedWIth.vue';
import FooterSektion from '@/components/FooterSektion.vue';
import MyWorkVue from '@/components/MyWork.vue';
import FooterFInal from '@/components/FooterFInal.vue';
import { onMounted, ref } from 'vue';
let showSection = ref('')
onMounted(() => {
  const observer = new IntersectionObserver((entries) => {
    entries.forEach((entry) => {
        if (entry.isIntersecting) {
          showSection.value = entry.target.id
        }
    })
  },
  {
    threshold: 0.5,
  })
  document.querySelectorAll('.section').forEach((section) => {
    observer.observe(section)
  });
})

</script>

<template>
  <main>
    <HeaderSection v-if="showSection === 'header' || 'WorkedWith'" class="section" id="header"/>
    <WorkedWIthVue v-if="showSection === 'header' || 'WorkedWith'" class="section" id="WorkedWith"/>
    <FooterSektion v-if="showSection === 'FooterSektion' || 'WorkedWith' || 'MyWork'" class="section" id="FooterSektion"/>
    <MyWorkVue v-if="showSection === 'FooterSektion' || 'WorkedWith' || 'FooterFInal'" class="section" id="MyWork" />
    <FooterFInal v-if="showSection === 'FooterFInal' || 'FooterSektion'" class="section" id="FooterFInal" />
  </main>
</template>

<style>
main {
  width: 100%;
}


</style>