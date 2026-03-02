<script setup lang="ts">
const props = defineProps({
  layoutClass: {
    type: String,
  },
})
</script>

<template>
  <div class="slidev-layout two-columns h-full" :class="props.layoutClass">
    <!-- Ewentualny slot bazowy dla nagłówka u góry -->
    <div class="col-span-2 mb-4">
      <slot />
    </div>

    <!-- Pół lewe - Bad -->
    <div class="two-cols-left col-span-1 flex flex-col justify-start p-8 bg-[#18181b] border-2 border-[#27272a] rounded-xl text-zinc-400 mr-4 shadow-lg shadow-black/50">
      <div class="text-red-500/80 mb-6 flex items-center gap-4">
        <div class="w-12 h-12 rounded-full bg-red-500/10 flex items-center justify-center">
            <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M18 6 6 18"/><path d="m6 6 12 12"/></svg>
        </div>
        <span class="text-2xl font-bold uppercase tracking-widest text-red-500/70">BAD</span>
      </div>
      <div class="comparison-content">
        <slot name="left" />
      </div>
    </div>
    
    <!-- Pół prawe - Good -->
    <div class="two-cols-right col-span-1 flex flex-col justify-start p-8 bg-[#2e1065]/20 border-2 border-brand-primary/50 border-glow rounded-xl ml-4 shadow-2xl shadow-brand-primary/20 relative overflow-hidden">
      <!-- Glow effect -->
      <div class="absolute -top-10 -right-10 w-32 h-32 bg-brand-primary/30 blur-3xl rounded-full"></div>
      
      <div class="text-brand-primary mb-6 flex items-center gap-4 relative z-10">
        <div class="w-12 h-12 rounded-full bg-brand-primary/20 flex items-center justify-center">
            <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><path d="M20 6 9 17l-5-5"/></svg>
        </div>
        <span class="text-2xl font-bold uppercase tracking-widest text-brand-primary">GOOD</span>
      </div>
      <div class="comparison-content relative z-10">
        <slot name="right" />
      </div>
    </div>
  </div>
</template>

<style scoped>
.comparison-content :deep(h1),
.comparison-content :deep(h2) {
  margin-top: 0;
  margin-bottom: 1rem;
}
.comparison-content :deep(ul) {
  padding-left: 1.5rem;
}
</style>
