<script setup lang="ts">
import puebloMagicos from '@/assets/img/icons/pueblo_magicos.svg'
import favicon from '@/assets/img/icons/favicon.svg'
import CarouselCards from '@/components/Carrousel.vue'
import atractiveCards from '@/data/atractivesCards'
import LiveItsMagic from '@/components/LiveItsMagic.vue'

</script>

<template>
  <main class="bg-[#131313]">
    <section
      id="home"
      class="w-full h-[100vh] relative bg-cover bg-center"
      style="background-image: url('src/assets/img/icons/HGO_REAL_DEL_MONTE.jpg')"
    >
      <div class="absolute inset-0 bg-black/70 z-10"></div>
      <div class="relative z-20 flex flex-col items-center justify-start h-full pt-10">
        <div class="flex items-center mb-6 space-x-4">
          <img :src="favicon" alt="Icono" class="w-16 h-16 animate-spin-slow" />
          <img :src="puebloMagicos" alt="Pueblos Mágicos" class="w-64 h-auto" />
        </div>
        <h1 class="text-4xl font-bold text-white text-center px-4">Bienvenido a la Página Principal</h1>
      </div>
    </section>

    <!-- Atractivos -->
    <section id="atractives" class="mt-10 mb-10 px- max-w-7xl mx-auto text-white">
      <h2 class="text-4xl font-bold mb-6 text-center">Atractivos</h2>
      <CarouselCards :items="atractiveCards" />
    </section>

    <!-- Vive su Magia -->
    <section id="liveitsmagic" class="mt-10 px- pl-10 max-w-7xl mx-auto text-white align-center">
      <h2 class="text-4xl font-bold mb-6 text-center">Vive su magia</h2>
      <LiveItsMagic />
    </section>

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
