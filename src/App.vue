<script setup lang="ts">
import NavigationBar from "./components/NavigationBar.vue";
import HeroSection from "./components/HeroSection.vue";
import AboutSection from "./components/AboutSection.vue";
import ExperienceSection from "./components/ExperienceSection.vue";
import ProjectsSection from "./components/ProjectsSection.vue";
import ContactSection from "./components/ContactSection.vue";
</script>

<template>
  <div id="app">
    <NavigationBar />
    <main>
      <HeroSection />
      <AboutSection />
      <ExperienceSection />
      <ProjectsSection />
      <ContactSection />
    </main>
  </div>
</template>

<style>
#app {
  width: 100%;
  overflow-x: hidden;
}

main {
  width: 100%;
}
</style>
