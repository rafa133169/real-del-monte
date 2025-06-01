<script setup lang="ts">
import { ref, onMounted } from 'vue'
import axios from 'axios'

const weather = ref<{
  description: string
  temp: number
  humidity: number
  icon: string
} | null>(null)

const loader = ref(false)

const API_KEY = import.meta.env.VITE_OPEN_WEATHER_API

onMounted(async () => {
  loader.value = true
  try {
    const { data } = await axios.get(
      `https://api.openweathermap.org/data/2.5/weather?q=Real del Monte,mx&units=metric&appid=${API_KEY}&lang=es`
    )

    weather.value = {
      description: data.weather[0].description,
      temp: data.main.temp,
      humidity: data.main.humidity,
      icon: `https://openweathermap.org/img/wn/${data.weather[0].icon}@2x.png`
    }
  } catch (error) {
    console.error('Error al obtener el clima:', error)
  } finally {
    loader.value = false
  }
})
</script>

<template>
  <div v-if="loader" class="flex items-center justify-center align-center h-16">
    <div class="flex space-x-2">
      <div class="w-3 h-3 bg-white rounded-full animate-bounce"></div>
      <div class="w-3 h-3 bg-white rounded-full animate-bounce [animation-delay:-0.2s]"></div>
      <div class="w-3 h-3 bg-white rounded-full animate-bounce [animation-delay:-0.4s]"></div>
    </div>
  </div>
  <div v-if="weather" class="rounded-xl text-white w-fit">
    <div class="flex flex-row items-center align-center space-x-4">
      <img :src="weather.icon" :alt="weather.description" class="w-12 h-12" />
      <div class="text-center flex align-center justify-center space-x-4 gap-5">
        <div class="flex flex-col align-center">
          <p class="text-sm text-white font-semibold">Clima actual</p>
          <p class="text-sm font-semibold capitalize text-white/70">{{ weather.description }}</p>
        </div>
        <div class="flex flex-col align-center">
          <p class="text-3xl">{{ Math.round(weather.temp) }}°</p>
        </div>
        <div class="w-px h-12 bg-white border"></div>
        <div class="flex flex-col align-center">
          <p class="text-sm text-white/70">Humedad</p>
          <p class="text-lg text-white font-semibold">{{ weather.humidity }}%</p>
        </div>
      </div>
    </div>
  </div>
</template>
