<script setup>
import Icon from './icons/Icon.vue';
import ProfileCard from './components/ProfileCard.vue';
import PrifleAbout from './components/ProfileAbout.vue';
import ProjectsList from './components/ProjectsList.vue';
import Footer from './components/Footer.vue';
</script>

<template>
  <header>
    <div class="flex gap-4 items-center">
      <Icon />
      <h1 class="text-2xl text-white">Mis proyectos</h1>
    </div>
  </header>

  <main class="max-w-2xl m-auto mt-4 flex flex-col">

    <div class="profile-container flex flex-col">
      <ProfileCard />
      <PrifleAbout class="my-8"/>
    </div>

    <div class="projects-container ">
      <h3 class="text-lg text-white">Proyectos</h3>

      <ProjectsList class="mt-4" />
    </div>
    
  </main>

  <Footer />
</template>

<style scoped>
header {
  padding: 8px;
}
</style>
