<template>
  <nav class="fixed z-50 w-1/5 h-[100vh] bg-gradient-to-r from-black via-black to-black/0 text-white m-0 flex flex-col items-center justify-center">
    <ul class="w-full h-2/3 flex flex-col justify-between items-start px-[5rem]">
      <li
        v-for="(item, index) in menuItems"
        :key="index"
        @mouseenter="hovered = index"
        @mouseleave="hovered = null"
        @click="item.hash && goToSection(item.hash)"
        class="flex items-center gap-4 transition-all duration-200 ease-in-out group cursor-pointer"
      >
        <img
          :src="hovered === index ? item.iconHover : item.icon"
          alt="icon"
          class="w-6 h-6 transition-transform duration-200 ease-in-out group-hover:scale-110 cursor-pointer"
        />
        <span
          class="font-bold text-xl text-white group-hover:text-[#C48701] transition-all duration-300 ease-in-out"
          :class="{ 'opacity-100 ml-2': hovered === index, 'opacity-0 ml-[-10px]': hovered !== index }"
        >
          {{ item.text }}
        </span>
      </li>
    </ul>
  </nav>
</template>

<script setup lang="ts">
import { ref } from 'vue'
import { useRouter } from 'vue-router'

const router = useRouter()
const hovered = ref<number | null>(null)

const menuItems = [
  {
    text: 'Home',
    icon: new URL('@/assets/img/icons/home.png', import.meta.url).href,
    iconHover: new URL('@/assets/img/icons/home_gold.png', import.meta.url).href,
  },
  {
    text: 'Buscar',
    icon: new URL('@/assets/img/icons/buscar.png', import.meta.url).href,
    iconHover: new URL('@/assets/img/icons/buscar_gold.png', import.meta.url).href,
  },
  {
    text: 'Vive su magia',
    icon: new URL('@/assets/img/icons/carteles.svg', import.meta.url).href,
    iconHover: new URL('@/assets/img/icons/carteles_gold.svg', import.meta.url).href,
    hash: '#liveitsmagic'
  },
  {
    text: 'Atractivos',
    icon: new URL('@/assets/img/icons/piramide.svg', import.meta.url).href,
    iconHover: new URL('@/assets/img/icons/piramide_gold.svg', import.meta.url).href,
    hash: '#atractives'
  },
  {
    text: 'Festividades',
    icon: new URL('@/assets/img/icons/festividades.svg', import.meta.url).href,
    iconHover: new URL('@/assets/img/icons/festividades_gold.svg', import.meta.url).href,
    hash: '#festivities'
  },
  {
    text: 'Hoteles',
    icon: new URL('@/assets/img/icons/hoteles.svg', import.meta.url).href,
    iconHover: new URL('@/assets/img/icons/hoteles_gold.svg', import.meta.url).href,
    hash: '#hotels'
  },
  {
    text: 'Restaurantes',
    icon: new URL('@/assets/img/icons/restaurantes.svg', import.meta.url).href,
    iconHover: new URL('@/assets/img/icons/restaurantes_gold.svg', import.meta.url).href,
  },
  {
    text: 'Tours',
    icon: new URL('@/assets/img/icons/tours.svg', import.meta.url).href,
    iconHover: new URL('@/assets/img/icons/tours_gold.svg', import.meta.url).href,
  },
  {
    text: 'Menu',
    icon: new URL('@/assets/img/icons/menu.png', import.meta.url).href,
    iconHover: new URL('@/assets/img/icons/menu_gold.png', import.meta.url).href,
  },
]

function goToSection(hash?: string) {
  if (hash) {
    router.push({ path: '/', hash })
  }
}
</script>

<style scoped>
li span {
  transition: all 0.3s ease;
  white-space: nowrap;
}
</style>
