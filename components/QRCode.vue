<script setup lang="ts">
import QrcodeVue from 'qrcode.vue'

const props = defineProps({
  value: {
    type: String,
    required: true
  },
  size: {
    type: Number,
    default: 300
  },
  color: {
    type: String,
    default: '#000000'
  },
  bgColor: {
    type: String,
    default: '#ffffff'
  }
})
</script>

<template>
  <QrcodeVue 
    :value="value" 
    :size="size" 
    render-as="svg" 
    :foreground="color" 
    :background="bgColor" 
    class="w-full h-full"
  />
</template>
