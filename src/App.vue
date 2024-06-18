<script setup>
import Icon from './icons/Icon.vue';
import ProfileCard from './components/ProfileCard.vue';
import PrifleAbout from './components/ProfileAbout.vue';
import ProjectsList from './components/ProjectsList.vue';
import Footer from './components/Footer.vue';
import { ref, onMounted } from 'vue';

onMounted(() => {
  document.documentElement.classList.add('dark');
});

const theme = ref('dark');

function changeTheme() {
  if (document.documentElement.classList.contains('dark')) {
    document.documentElement.classList.remove('dark');
    theme.value = 'light';
  } else {
    document.documentElement.classList.add('dark');
    theme.value = 'dark';
  }
}

const styles = {
  mainText: 'text-lg text-black dark:text-white'
} 
</script>

<template>
  <header class="flex justify-between items-center">
    <div class="flex gap-4 items-center">
      <Icon />
      <h1 class="text-2xl text-black dark:text-white">Mis proyectos</h1>
    </div>

    <button 
      class="text-black dark:text-white" 
      @click="changeTheme"
    >
      {{ theme }}
      <i 
        class="pi pi-moon text-black dark:text-white">
      </i>
    </button>
  </header>

  <main class="max-w-2xl m-auto mt-4 flex flex-col">

    <div class="profile-container flex flex-col">
      <ProfileCard />
      <PrifleAbout class="my-8"/>
    </div>

    <div class="projects-container">
      <h3 :class="styles.mainText">Proyectos</h3>

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
