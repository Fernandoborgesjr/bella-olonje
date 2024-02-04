<script setup lang="ts">
import { RouterView } from 'vue-router'
import NavBar from './components/NavBar.vue'
import FooterBar from './components/FooterBar.vue'
</script>

<template>
  <div class="flex flex-col h-screen">
    <header class="container mx-auto p-4">
      <NavBar />
    </header>

    <RouterView class="flex-1" />

    <FooterBar />
  </div>
</template>
