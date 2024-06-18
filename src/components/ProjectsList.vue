<script setup>
const projects = [
  {
    title: 'Personal finance balance',
    description: 'Esta plataforma permite a los usuarios gestionar sus gastos, ingresos y deudas, clasificándolos según su fuente.',
    years: '2024',
    backendTools: ['Nestjs', 'Postgres', 'Sequelize'],
    backendLink: 'https://github.com/Edkiri/personal-finance-api',
    frontendTools: ['Vite', 'Vue', 'Typescript', 'Pinia', 'Tailwind'],
    frontendLink: 'https://github.com/Edkiri/personal-finance-front',
    link: '',
  },
  {
    title: 'Sistema de Punto de Venta - Web',
    description: 'App web para la gestión de ventas e inventario de productos.',
    years: '2023 - ahora',
    backendTools: ['Nestjs', 'Postgres', 'Prisma', 'Swagger'],
    backendLink: 'https://github.com/Edkiri/sales-nest-api',
    frontendTools: ['Vite', 'Vue', 'Typescript', 'Tailwind'],
    frontendLink: 'https://github.com/Edkiri/sales-ui',
    link: '',
  },
  {
    title: 'Sistema de Punto de Venta - Desktop',
    description: 'Desktop app para la gestión de ventas e inventario de productos.',
    years: '2021 - 2023',
    backendTools: ['Python', 'TKinter', 'Sqlite', 'Peewee ORM', 'Pandas', 'Numpy'],
    backendLink: 'https://github.com/Edkiri/Ironmongery/tree/feat/stock',
    frontendTools: [],
    frontendLink: '',
    link: '',
  },
  {
    title: 'Organizador de tareas',
    description: 'Es un clon de Microsoft Todo App. Permite a los usuarios crear listas y tareas; mover, borrar, completar tareas, marcar fecha límite...',
    years: '2023',
    backendTools: ['Nestjs', 'Postgres', 'Typeorm', 'Luxon', 'Google OAuth2'],
    backendLink: 'https://github.com/Edkiri/task-api',
    frontendTools: ['Vite', 'React', 'Typescript', 'TanStack Query', 'Material UI'],
    frontendLink: 'https://github.com/Edkiri/task-ui',
    link: '',
  },
  {
    title: 'Mastermind',
    description: 'Simulador web del juego de mesa Mastermind.',
    years: '2023',
    backendTools: ['Html', 'Css', 'Javascript', 'Programación reactiva'],
    backendLink: 'https://github.com/Edkiri/mastermind',
    frontendTools: [],
    frontendLink: '',
    link: 'https://edkiri.github.io/mastermind/',
  },
  {
    title: 'Quinielas',
    description: 'Esta aplicación permite a los usuarios crear grupos, predecir resultados de partidos de fútbol, ganar puntos por aciertos y competir entre sí. También pueden enviar y recibir invitaciones para unirse a grupos.',
    years: '2022',
    backendTools: ['Nestjs', 'Postgres', 'TypeORM', 'Luxon', 'Passport'],
    backendLink: 'https://github.com/Edkiri/predikete-api',
    frontendTools: ['React'],
    frontendLink: 'https://github.com/Edkiri/predikete-ui',
    link: '',
  },
]; 

const styles = {
  titleText: 'text-black dark:text-white',

}
</script>

<template>
  <div class="flex flex-col gap-16">
    <div v-for="project in projects" class="flex">
      <div class="flex flex-col gap-2 w-full">
        <div class="title flex gap-2 justify-between">
          <h4 v-if="!project.link" :class="'text-base ' + styles.titleText">{{ project.title }}</h4>
          <a v-else target="_blank" :class="'text-base hover:underline hover:text-neutral-900 dark:hover:text-neutral-900' + styles.titleText" :href="project.link">{{ project.title }}<i class="pi pi-arrow-up-right ml-1" style="color: rgb(115, 115, 115); font-size: 10px"></i></a>
          <p class="text-neutral-700 dark:text-neutral-300 text-base">{{ project.years }}</p>
        </div>
        <p class="text-neutral-600 dark:text-neutral-400 text-base">{{ project.description }}</p>
        <div class="flex flex-col gap-3 mt-2">
          <div class="flex flex-col gap-1">
            <a target="_blank" class="mt-1 flex items-center gap-2" :href="project.backendLink">
              <i class="pi pi-github" style="color: rgb(163 163 163);"></i>
              <p class="text-base text-neutral-700 dark:text-neutral-400 hover:underline hover:text-neutral-900 dark:hover:text-neutral-300">
                {{ project.frontendTools.length ? 'Backend' :  'Repositorio' }}
              </p>
              <i class="pi pi-arrow-up-right" style="color: rgb(115, 115, 115); font-size: 10px"></i>
            </a>
            <div class="flex gap-1">
              <p 
              class="text-neutral-700 dark:text-neutral-400 bg-neutral-200 dark:bg-neutral-800 rounded-full px-3 inline-block " 
              v-for="tool in project.backendTools">
              {{ tool }}
            </p>
            </div>
          </div>
          <div class="flex flex-col gap-1">
            <a v-if="project.frontendTools.length" target="_blank" class="mt-1 flex items-center gap-2" :href="project.frontendLink">
              <i class="pi pi-github" style="color: rgb(163 163 163);"></i>
              <p class="text-base text-neutral-700 dark:text-neutral-400 hover:underline hover:text-neutral-900 dark:hover:text-neutral-300">
                Frontend
              </p>
              <i class="pi pi-arrow-up-right" style="color: rgb(115, 115, 115); font-size: 10px"></i>
            </a>
            <div class="flex gap-1">
              <p 
              class="text-neutral-700 dark:text-neutral-400 bg-neutral-200 dark:bg-neutral-800 rounded-full px-3 inline-block " 
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