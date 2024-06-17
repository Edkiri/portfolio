<script setup>
const projects = [
  {
    title: 'FinanSave',
    description: 'Esta plataforma permite a los usuarios gestionar sus gastos, ingresos y deudas, clasificándolos según su fuente.',
    years: '2024',
    backendTools: ['Nestjs', 'Postgres', 'Sequelize'],
    backendLink: 'https://github.com/Edkiri/personal-finance-api',
    frontendTools: ['Vite', 'Vue', 'Typescript', 'Pinia', 'Tailwind'],
    frontendLink: 'https://github.com/Edkiri/personal-finance-front',
  },
  {
    title: 'Sistema de Punto de Venta',
    description: 'App web para la gestión de ventas e inventario de productos.',
    years: '2023 - ahora',
    backendTools: ['Nestjs', 'Postgres', 'Prisma', 'Swagger'],
    backendLink: 'https://github.com/Edkiri/sales-nest-api',
    frontendTools: ['Vite', 'Vue', 'Typescript', 'Tailwind'],
    frontendLink: 'https://github.com/Edkiri/sales-ui',
  },
  {
    title: 'TodoApp',
    description: 'Es un clon de Microsoft Todo App. Permite a los usuarios crear listas y tareas; mover, borrar, completar tareas, marcar fecha límite...',
    years: '2023',
    backendTools: ['Nestjs', 'Postgres', 'Typeorm', 'Luxon', 'Google OAuth2'],
    backendLink: 'https://github.com/Edkiri/task-api',
    frontendTools: ['Vite', 'React', 'Typescript', 'TanStack Query', 'Material UI'],
    frontendLink: 'https://github.com/Edkiri/task-ui',
  },
  
]; 
</script>

<template>
  <div class="flex flex-col gap-12">
    <div v-for="project in projects" class="flex">
      <p class="text-neutral-500 text-base min-w-36">{{ project.years }}</p>
      <div class="flex flex-col gap-2">
        <h4 class="text-white text-base">{{ project.title }}</h4>
        <p class="text-neutral-400 text-base">{{ project.description }}</p>
        <div class="flex flex-col gap-1">
          <a target="_blank" class="group mt-1 flex items-center gap-2" :href="project.backendLink">
            <i class="pi pi-github" style="color: rgb(163 163 163);"></i>
            <p class="text-base text-neutral-400 group-hover:underline group-hover:text-neutral-300">
              Backend
            </p>
            <i class="pi pi-arrow-up-right" style="color: rgb(115, 115, 115); font-size: 10px"></i>
          </a>
          <p class="text-base text-neutral-500">{{ project.backendTools.join(" - ") }}</p>
          <a target="_blank" class="group mt-1 flex items-center gap-2" :href="project.frontendLink">
            <i class="pi pi-github" style="color: rgb(163 163 163);"></i>
            <p class="text-base text-neutral-400 group-hover:underline group-hover:text-neutral-300">
              Frontend
            </p>
            <i class="pi pi-arrow-up-right" style="color: rgb(115, 115, 115); font-size: 10px"></i>
          </a>
          <p class="text-base text-neutral-500">{{ project.frontendTools.join(" - ") }}</p>
        </div>
      </div>
    </div>
  </div>
</template>