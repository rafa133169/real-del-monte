<script setup lang="ts">
import { onMounted, ref } from 'vue'

defineProps<{
  items: {
    title: string
    place: string
    image: string
  }[]
}>()

const containerRef = ref<HTMLElement | null>(null)

onMounted(() => {
  const container = containerRef.value
  if (!container) return

  let isDown = false
  let startX: number
  let scrollLeft: number

  container.addEventListener('mousedown', (e) => {
    isDown = true
    container.classList.add('cursor-grabbing')
    startX = e.pageX - container.offsetLeft
    scrollLeft = container.scrollLeft
  })

  container.addEventListener('mouseleave', () => {
    isDown = false
    container.classList.remove('cursor-grabbing')
  })

  container.addEventListener('mouseup', () => {
    isDown = false
    container.classList.remove('cursor-grabbing')
  })

  container.addEventListener('mousemove', (e) => {
    if (!isDown) return
    e.preventDefault()
    const x = e.pageX - container.offsetLeft
    const walk = (x - startX) * 8.5
    container.scrollLeft = scrollLeft - walk
  })
})
</script>

<template>
  <div class="relative overflow-hidden px-4 p-6 flex">
    <div class="w-1/10 pr-4">
      <p class="text-white"></p>
    </div>
<br>
    <div class="w-9/10">
      <br>
      <div
        ref="containerRef"
        class="scrollbar-hide overflow-x-auto scroll-smooth -mx-4 pr-4 cursor-grab select-none"
      >
        <div class="flex space-x-16 w-max h-full">
          <div
            v-for="(item, index) in items"
            :key="index"
            class="relative w-[250px] h-[250px] rounded-2xl overflow-hidden border-8 border-white shadow-lg bg-black flex-shrink-0"
          >
            <img :src="item.image" alt="" class="w-full h-full object-cover opacity-80" />
            <div class="absolute bottom-0 w-full p-4 bg-gradient-to-t from-black via-transparent to-transparent">
              <p class="text-sm text-white/80">{{ item.place }}</p>
              <h3 class="text-white text-lg font-bold leading-tight">{{ item.title }}</h3>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.cursor-grab {
  cursor: grab;
}
.cursor-grabbing {
  cursor: grabbing;
}
</style>
