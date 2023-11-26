<script setup lang="ts">
import { ref } from "vue";
import { InputField, FormField } from "@/components"
const msg = ref("Vite + Vue 3 + Typescript + Tailwindcss v3");

const data = {
  name: "Oklee",
  tel: '0988777666',
  address: 'NewYork, America',
  description: 'none'
}
</script>

<template>
  <h1>{{ msg }}</h1>
  <FormField v-model="data">
    <InputField class="border p-2" name="name" type="text" v-model="msg" />
    <div class="p-5">
      tel:
      <InputField class="border p-2" name="tel" type="text" />
    </div>
    <InputField class="border p-2" name="address" type="text" />
    <InputField class="border p-2" name="description" type="text" />
  </FormField>
</template>

<style></style>
