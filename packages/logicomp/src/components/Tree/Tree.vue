<script setup lang="ts">
import { onMounted, VNode, } from 'vue'
type nodeType = Object | string

const props = defineProps<{
  node: VNode
  is?: any
}>()

const typeCheck = (type) => {
  return type instanceof Object || typeof type === 'string'
}

onMounted(() => {
})
</script>

<template>
  <component v-if="typeCheck(node.type)" :is="node.type" v-bind="node.props">
    <Tree v-if="node.children" v-for="(childNode, index) in (node.children as VNode[])" :key="index" :is="childNode.type"
      v-bind="childNode.props" :node="childNode" />
  </component>
  <component v-else v-text="node.children" />
</template>