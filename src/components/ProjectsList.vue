<script setup>
import { computed } from 'vue';

const projects = [
  {
    id: 1,
    title: 'Cash Save',
    description: 'Esta plataforma permite a los usuarios gestionar sus gastos, ingresos y deudas, clasificándolos según su fuente.',
    years: '2024',
    backendTools: ['Nestjs', 'Postgres', 'Sequelize'],
    backendLink: 'https://github.com/Edkiri/personal-finance-api',
    frontendTools: ['Vite', 'Vue', 'Typescript', 'Pinia', 'Tailwind'],
    frontendLink: 'https://github.com/Edkiri/personal-finance-front',
    link: 'https://cashsave.eduardok.site',
    image: 'app-dark.png',
  },
  {
    id: 2,
    title: 'Sistema de Punto de Venta - Web',
    description: 'App web para la gestión de ventas e inventario de productos.',
    years: '2023 - ahora',
    backendTools: ['Nestjs', 'Postgres', 'Prisma', 'Swagger'],
    backendLink: 'https://github.com/Edkiri/sales-nest-api',
    frontendTools: ['Vite', 'Vue', 'Typescript', 'Tailwind'],
    frontendLink: 'https://github.com/Edkiri/sales-ui',
    link: '',
    image: '',
  },
  {
    id: 3,
    title: 'Sistema de Punto de Venta - Desktop',
    description: 'Desktop app para la gestión de ventas e inventario de productos.',
    years: '2021 - 2023',
    backendTools: ['Python', 'TKinter', 'Sqlite', 'Peewee ORM', 'Pandas', 'Numpy'],
    backendLink: 'https://github.com/Edkiri/Ironmongery/tree/feat/stock',
    frontendTools: [],
    frontendLink: '',
    link: '',
    image: '',
  },
  {
    id: 4,
    title: 'Organizador de tareas',
    description: 'Es un clon de Microsoft Todo App. Permite a los usuarios crear listas y tareas; mover, borrar, completar tareas, marcar fecha límite...',
    years: '2023',
    backendTools: ['Nestjs', 'Postgres', 'Typeorm', 'Luxon', 'Google OAuth2'],
    backendLink: 'https://github.com/Edkiri/task-api',
    frontendTools: ['Vite', 'React', 'Typescript', 'TanStack Query', 'Material UI'],
    frontendLink: 'https://github.com/Edkiri/task-ui',
    link: '',
    image: '',
  },
  {
    id: 5,
    title: 'Mastermind',
    description: 'Simulador web del juego de mesa Mastermind.',
    years: '2023',
    backendTools: ['Html', 'Css', 'Javascript', 'Programación reactiva'],
    backendLink: 'https://github.com/Edkiri/mastermind',
    frontendTools: [],
    frontendLink: '',
    link: 'https://edkiri.github.io/mastermind/',
    image: 'mastermind.png',
  },
  {
    id: 6,
    title: 'Quinielas',
    description: 'Esta aplicación permite a los usuarios crear grupos, predecir resultados de partidos de fútbol, ganar puntos por aciertos y competir entre sí. También pueden enviar y recibir invitaciones para unirse a grupos.',
    years: '2022',
    backendTools: ['Nestjs', 'Postgres', 'TypeORM', 'Luxon', 'Passport'],
    backendLink: 'https://github.com/Edkiri/predikete-api',
    frontendTools: ['React'],
    frontendLink: 'https://github.com/Edkiri/predikete-ui',
    link: '',
    image: '',
  },
]; 

const props = defineProps({
  theme: {
    type: String,
    required: false,
  },
});

const saveCashImage = computed(() => {
  return props.theme === 'dark' ? 'cash-save-dark.png' : 'cash-save-light.png'; 
});

</script>

<template>
  <div class="flex flex-col gap-8">
    <div v-for="project in projects" class="flex border-2 rounded-md border-neutral-300 dark:border-neutral-700 p-6 ">
      <div class="flex flex-col gap-2 w-full">
        <div class="title flex gap-2 justify-between">
          <h4 v-if="!project.link" :class="'text-xl font-semibold text-black dark:text-white'">{{ project.title }}</h4>
          <a v-else target="_blank" :class="'text-xl font-semibold hover:underline text-black dark:text-white'" :href="project.link">{{ project.title }}<i class="pi pi-arrow-up-right ml-1" style="color: rgb(115, 115, 115); font-size: 14px; margin-left: 8px;"></i></a>
          <p class="text-neutral-800 dark:text-neutral-200 text-lg">{{ project.years }}</p>
        </div>
        <p class="text-neutral-800 dark:text-neutral-200 text-base">{{ project.description }}</p>
        
        <a v-if="project.image" target="_blank" class="w-full" :href="project.link">
          <img v-if="project.id === 1" class="w-full px-8 my-2 rounded-md" :src="`/${saveCashImage}`" alt="cash save app">
          <img v-if="project.id === 5" class="w-[300px] mx-auto my-2 rounded-md" :src="`/${project.image}`" alt="mastermind online">
        </a>

        <div class="flex flex-col gap-4 mt-2">
          <div class="flex flex-col gap-2">
            <a target="_blank" class="mt-1 flex items-center gap-2" :href="project.backendLink">
              <i class="pi pi-github" style="color: rgb(163 163 163);"></i>
              <p class="text-lg font-semibold text-neutral-800 dark:text-neutral-200 hover:underline hover:text-neutral-900 dark:hover:text-neutral-300">
                {{ project.frontendTools.length ? 'Backend' :  'Repositorio' }}
              </p>
              <i class="pi pi-arrow-up-right" style="color: rgb(115, 115, 115); font-size: 14px"></i>
            </a>
            <div class="flex gap-2">
              <p 
                class="text-neutral-800 dark:text-neutral-200 bg-neutral-200 dark:bg-neutral-800 rounded-full px-3 inline-block " 
                v-for="tool in project.backendTools">
                {{ tool }}
            </p>
            </div>
          </div>
          <div class="flex flex-col gap-2">
            <a v-if="project.frontendTools.length" target="_blank" class="mt-1 flex items-center gap-2" :href="project.frontendLink">
              <i class="pi pi-github" style="color: rgb(163 163 163);"></i>
              <p class="text-lg font-semibold text-neutral-800 dark:text-neutral-200 hover:underline hover:text-neutral-900 dark:hover:text-neutral-300">
                Frontend
              </p>
              <i class="pi pi-arrow-up-right" style="color: rgb(115, 115, 115); font-size: 14px"></i>
            </a>
            <div class="flex gap-2">
              <p 
              class="text-neutral-800 dark:text-neutral-200 bg-neutral-200 dark:bg-neutral-800 rounded-full px-3 inline-block " 
              v-for="tool in project.frontendTools">
              {{ tool }}
            </p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>