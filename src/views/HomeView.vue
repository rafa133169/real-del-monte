<script setup lang="ts">
import puebloMagicos from '@/assets/img/icons/pueblo_magicos.svg'
import favicon from '@/assets/img/icons/favicon.svg'
import CarouselCards from '@/components/Carrousel.vue'
import atractiveCards from '@/data/atractivesCards'
import LiveItsMagic from '@/components/LiveItsMagic.vue'
import Weather from '@/components/Weather.vue'
import location from '@/assets/img/hidalgo-location.png'
import Imprescindibles from '@/components/Imprescindibles.vue'
import hotelsCard from '@/data/hotelsCards'
import restaurantsCards from '@/data/restaurantsCards'
import festivitiesCards from '@/data/festivitiesCardas'


</script>

<template>
  <main class="bg-[#131313]">
    <section
      id="home"
      class="w-full h-[100vh] relative bg-cover bg-center"
      style="background-image: url('src/assets/img/icons/HGO_REAL_DEL_MONTE.jpg')"
    >
      <div class="absolute inset-0 bg-black/70 z-10">
        <div class="relative z-20 flex flex-col items-center h-full pt-10">
          <div class="flex items-center mb-6 space-x-4">
            <img :src="favicon" alt="Icono" class="w-16 h-16 animate-spin-slow" />
            <img :src="puebloMagicos" alt="Pueblos Mágicos" class="w-64 h-auto" />
          </div>
          <!-- Inicio -->
          <div class="flex flex-row items-center justify-between my-auto">
            <div class="flex flex-col items-start space-y-4">
              <div class="flex flex-col items-start gap-5">
                <h2 class="text-2xl font-bold text-white">Hidalgo</h2>
                <h1 class="text-4xl font-bold text-white">Real del Monte</h1>
                <p class="text-white text-xl">
                  Siéntate frente a una de las bellas plazas del Pueblo <br>
                  Mágico, mientras saboreas un delicioso paste y luego <br>
                  descubre sus rincones que conservan un dejo británico.
                </p>
              </div>
              <Weather />
            </div>
            <div class="flex flex-col items-center">
              <img :src="location" alt="Ubicación" class="w-74 h-52 mt-4" />
            </div>
          </div>
        </div>
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

    <!-- Imprescindible -->
    <section id="imprescindibles" class="mt-10 px- pl-10 max-w-7xl mx-auto text-white align-center">
      <h2 class="text-4xl font-bold mb-6 text-center">Imprescindibles</h2>
      <Imprescindibles />
    </section>

    <!-- Festividades -->
    <section id="festivities" class="mt-10 mb-10 px- max-w-7xl mx-auto text-white">
      <h2 class="text-4xl font-bold mb-6 text-center">Festividades</h2>
      <CarouselCards :items="festivitiesCards" />
    </section>

       <!-- Hoteles -->
    <section id="hotels" class="mt-10 mb-10 px- max-w-7xl mx-auto text-white">
      <h2 class="text-4xl font-bold mb-6 text-center">Hoteles</h2>
      <CarouselCards :items="hotelsCard" />
    </section>

       <!-- Restaurantes -->
    <section id="hotels" class="mt-10 mb-10 px- max-w-7xl mx-auto text-white">
      <h2 class="text-4xl font-bold mb-6 text-center">Restaurantes</h2>
      <CarouselCards :items="restaurantsCards" />
    </section>

       <!-- Tours -->
    <section id="hotels" class="mt-10 mb-10 px- max-w-7xl mx-auto text-white">
      <h2 class="text-4xl font-bold mb-6 text-center">Tours</h2>
      <CarouselCards :items="hotelsCard" />
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
