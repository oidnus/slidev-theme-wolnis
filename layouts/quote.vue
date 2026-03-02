<script setup lang="ts">
const props = defineProps({
  author: {
    type: String,
    default: '',
  },
})
</script>

<template>
  <div class="slidev-layout quote-layout h-full flex flex-col justify-center items-center text-center px-24">
    <div class="text-5xl font-heading font-bold text-zinc-100 mb-8 max-w-4xl relative quote-content">
      <span class="absolute -top-12 -left-16 text-8xl text-brand-primary opacity-40">"</span>
      <slot />
      <span class="absolute -bottom-16 -right-12 text-8xl text-brand-primary opacity-40">"</span>
    </div>
    <div v-if="author" class="text-3xl text-zinc-400 font-light mt-8">
      — {{ author }}
    </div>
  </div>
</template>

<style scoped>
.quote-content {
  line-height: 1.3 !important;
}
.quote-content :deep(p),
.quote-content :deep(h1),
.quote-content :deep(h2),
.quote-content :deep(h3) {
  line-height: 1.3 !important;
  margin-top: 0.5em;
  margin-bottom: 0.5em;
}
</style>
