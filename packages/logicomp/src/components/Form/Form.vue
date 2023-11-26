<script setup lang="ts">
import { useSlots, onMounted, ref, VNode } from 'vue';
import Tree from '@/components/Tree/Tree.vue'

const slots = ref<VNode[]>([])

onMounted(() => {
  const slotDefault = useSlots().default;
  if (slotDefault instanceof Function) {
    slots.value = slotDefault()
    console.log(slots.value)
  }
})
</script>

<template>
  <form>
    <Tree v-for="slot of slots" :node="slot"></Tree>
  </form>
</template>