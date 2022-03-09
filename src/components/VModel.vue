<template>
  <!-- <input type="text" :childProps="fatherProps" @input="childEvent" /> -->
  <input type="text" :childProps="modelValue" @input="childEvent" />
  <hr />
  <!-- <p>{{ fatherProps }}</p> -->
  <p>modelValue: {{ modelValue }}</p>
</template>

<script setup lang="ts">
const props = defineProps({
  // fatherProps: {
  //   type: String,
  //   default: '',
  // },
  modelValue: {
    type: String,
    default: '',
  },
})

const emits = defineEmits<{
  // (e: 'childInputChange', data: string): void
  (e: 'update:modelValue', data: string): void
}>()

const childEvent = (e: Event) => {
  let childEventContent = (e.target as HTMLInputElement).value
  // emits('childInputChange', childEventContent)
  emits('update:modelValue', childEventContent)
}
</script>

<style>
input {
  display: block;
}
</style>
