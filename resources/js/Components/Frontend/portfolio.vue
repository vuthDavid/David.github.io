<script setup>
import Project from "./Project.vue";

defineProps({
  skills: Object,
  projects: Object,
});
</script>
<template>
  <section id="portfolio"
    class="section bg-light-secondary dark:bg-dark-navy-500  min-h-[1400px]"
  >
    <div class="container mx-auto"
        v-motion
        :initial="{
            opacity:0,
            y:100,
        }"    
        :visible="{
            opacity:1,
            y:0,
        }">
      <div class="flex flex-col items-center text-center">
        <h2 class="section-title">My latest work</h2>
        <p class="subtitle">
          Lorem ipsum dolor sit amet consectetur adipisicing elit. Harum
          necessitatibus excepturi impedit quasi repellendus totam obcaecati ab
        </p>
      </div>
    </div>
    <Project :skills="skills" :projects="projects" />
  </section>
</template>
