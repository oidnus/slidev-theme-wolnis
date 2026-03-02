<script setup lang="ts">
const props = defineProps({
  type: {
    type: String,
    default: 'primary' // 'primary' | 'error' | 'success' | 'warning'
  }
})

const colors = {
  primary: 'bg-brand-primary/20 text-brand-primary border-brand-primary/40',
  error: 'bg-red-500/10 text-red-500 border-red-500/30',
  success: 'bg-green-500/10 text-green-500 border-green-500/30',
  warning: 'bg-yellow-500/10 text-yellow-500 border-yellow-500/30',
}
</script>

<template>
  <span 
    class="inline-flex items-center px-2.5 py-0.5 rounded-full text-xs font-bold font-mono border uppercase tracking-widest align-middle mx-1"
    :class="colors[props.type] || colors.primary"
  >
    <slot />
  </span>
</template>
