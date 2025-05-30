<script setup lang="ts">
import puebloMagicos from '@/assets/img/icons/pueblo_magicos.svg'
import favicon from '@/assets/img/icons/favicon.svg'
import CarouselCards from '@/components/Carrousel.vue'

const realDelMonteCards = [
  {
    title: 'Descubre los rumbos del centro',
    place: 'REAL DEL MONTE',
    image: new URL('@/assets/img/atractives/55_RDM_Dulces_Tipicos.jpg', import.meta.url).href,
  },
  {
    title: 'Elabora tu paste',
    place: 'REAL DEL MONTE',
    image: new URL('@/assets/img/atractives/FD_20140519_654_HGO_REAL_DEL_MONTE_PASTES_EL_PORTAL_PASTES_CON_PAPA_RC.jpg', import.meta.url).href,
  },
  {
    title: 'La Peña del Zumate',
    place: 'REAL DEL MONTE',
    image: new URL('@/assets/img/atractives/Pena-del-Zumate-1.jpeg', import.meta.url).href,
  },
  {
    title: 'Mina de Acosta',
    place: 'REAL DEL MONTE',
    image: new URL('@/assets/img/atractives/Mina-de-Acosta.jpg', import.meta.url).href,
  },
]
</script>

<template>
  <main>
    <section id="home" class="w-full h-[100vh] bg-[url('src/assets/img/icons/HGO_REAL_DEL_MONTE.jpg')] bg-cover bg-center">
      <div class="bg-black/70 flex flex-col items-center justify-start h-full pt-10">
        <div class="flex items-center mb-6 space-x-4">
          <img :src="favicon" alt="Icono" class="w-16 h-16 animate-spin-slow" />
          <img :src="puebloMagicos" alt="Pueblos Mágicos" class="w-64 h-auto" />
        </div>
        <h1 class="text-4xl font-bold text-white">Bienvenido a la Página Principal</h1>
      </div>
    </section>

    <!-- Atractivos -->
    <!-- <section id="atractives" class="mt-10 px-4 max-w-5xl mx-auto">
      <h2 class="text-3xl font-bold mb-6 text-center">Atractivos</h2>
      <CarouselCards :items="realDelMonteCards" />
    </section> -->

  </main>
</template>

<style scoped>
@keyframes spin {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(360deg);
  }
}

.animate-spin-slow {
  animation: spin 5s linear infinite;
}
</style>
