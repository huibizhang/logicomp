<script setup lang="ts">
type modelValue = string | number;

const props = withDefaults(
  defineProps<{
    name?: string;
    type?: "text" | "number" | "range";
    modelValue?: modelValue;
    class?: string | Array<string>
  }>(),
  {
    name: "",
    type: "text",
    modelValue: "",
    class: ""
  }
);

const emit = defineEmits<{
  (event: "update:modelValue", value: modelValue): void;
}>();

const update = (evt: Event) => {
  let val: modelValue = (evt.target as HTMLInputElement)?.value;
  const isNum = ["number", "range"].includes(props.type);
  emit("update:modelValue", isNum ? Number(val) : val);
};
</script>

<template>
  <input :name="name ?? ''" :type="type" :value="modelValue" @input="update" :class="class" />
</template>
