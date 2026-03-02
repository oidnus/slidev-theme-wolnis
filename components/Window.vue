<script setup lang="ts">
const props = defineProps({
  title: {
    type: String,
    default: 'https://damianslimak.pl'
  },
  type: {
    type: String,
    default: 'browser' // 'browser' | 'terminal'
  }
})
</script>

<template>
  <div class="window-mockup flex flex-col rounded-xl overflow-hidden border border-zinc-700 shadow-2xl bg-[#18181b] w-full">
    <!-- Header -->
    <div class="bg-[#27272a] px-4 py-2 flex items-center gap-3 border-b border-zinc-700/50">
      <div class="flex gap-1.5 pt-0.5">
        <div class="w-2.5 h-2.5 rounded-full bg-red-500/60"></div>
        <div class="w-2.5 h-2.5 rounded-full bg-yellow-500/60"></div>
        <div class="w-2.5 h-2.5 rounded-full bg-green-500/60"></div>
      </div>
      
      <!-- Browser URL bar style -->
      <div v-if="props.type === 'browser'" class="flex-grow flex justify-center">
        <div class="bg-zinc-900/50 rounded-md px-3 py-0.5 text-[10px] text-zinc-500 border border-zinc-800 flex items-center gap-2 min-w-[200px]">
          <i class="i-fa7-solid-lock text-[8px] opacity-40"></i>
          {{ props.title }}
        </div>
      </div>
      
      <!-- Terminal title style -->
      <div v-else class="flex-grow text-center text-[10px] text-zinc-500 font-mono tracking-tight">
        {{ props.title || 'bash — 80×24' }}
      </div>
    </div>
    
    <!-- Content Area -->
    <div class="p-0 overflow-hidden leading-0 flex">
      <slot />
    </div>
  </div>
</template>

<style scoped>
.window-mockup :deep(img) {
  margin: 0 !important;
  display: block;
}
.window-mockup :deep(pre) {
  margin: 0 !important;
  border-radius: 0 !important;
}
</style>
