<script setup lang="ts">
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://v3.vuejs.org/api/sfc-script-setup.html#sfc-script-setup

import HelloWorld from "@/components/HelloWorld.vue";
</script>

<template>
  <div class="text-center selection:bg-green-100">
    <img class="mx-auto mb-8 mt-12" alt="Vue logo" src="./assets/logo.png" />
    <HelloWorld msg="Vite + Vue 3 + Typescript + Tailwindcss v3" />
    <img
      class="mx-auto my-8"
      alt="powered-by"
      src="./assets/powered-by-vitawind-bright.png"
    />
    <LogiButton class="border">123</LogiButton>
  </div>
</template>

<style></style>
