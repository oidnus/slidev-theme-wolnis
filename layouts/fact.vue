<script setup lang="ts">
const props = defineProps({
  fact: {
    type: String,
    required: true,
  },
  label: {
    type: String,
  },
})
</script>

<template>
  <div class="slidev-layout h-full flex flex-col justify-center items-center text-center px-14">
    <div class="text-brand-primary font-bold tracking-tight mb-4" style="font-size: 15rem; line-height: 1;">
      {{ props.fact }}
    </div>
    <div v-if="props.label" class="text-3xl text-zinc-300 font-light max-w-2xl px-8">
      {{ props.label }}
    </div>
    <div class="mt-8 text-xl text-zinc-500 max-w-2xl">
      <slot />
    </div>
  </div>
</template>
