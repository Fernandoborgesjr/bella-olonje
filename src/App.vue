<script setup lang="ts">
import { RouterView } from 'vue-router'
import NavBar from './components/NavBar.vue'
</script>

<template>
  <header class="container mx-auto p-4">
    <NavBar />
  </header>

  <RouterView />
</template>
