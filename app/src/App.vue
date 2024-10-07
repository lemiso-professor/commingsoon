<template>
  <div class="min-h-screen bg-white">
    <Header />
    <div class="mt-4">
      <RouterView />
    </div>
    <Cards />
  </div>
</template>

<script setup>
import { RouterView } from "vue-router";
import Header from "./components/Header.vue";
import Cards from "./components/Cards.vue";
</script>

<style scoped></style>
