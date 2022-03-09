<template>
  <!-- <VModel :fatherProps="fatherContents" @childInputChange="fatherResponse"></VModel> -->
  <VModel v-model="fatherContents"></VModel>
</template>

<script setup lang="ts">
import { ref } from 'vue'
import VModel from './components/VModel.vue'

const fatherContents = ref("this is father's content")

const fatherResponse = (data: string) => {
  console.log('father response the emit event, and the data is:', data)
  fatherContents.value = data
}
</script>
