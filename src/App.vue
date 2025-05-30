<script setup lang="ts">
import { RouterView } from 'vue-router'
import Sidebar from '@/components/Sidebar.vue'
</script>

<template>
  <div class="flex">
    <Sidebar />
    <div class="flex-1">
      <RouterView />
    </div>
  </div>
</template>
