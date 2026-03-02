<template>
  <div
    v-if="$slidev.configs.showSlideNumber"
    class="absolute bottom-4 right-6 text-sm text-zinc-500 font-mono z-50 pointer-events-none"
  >
    {{ $slidev.nav.currentPage }} / {{ $slidev.nav.total }}
  </div>
</template>
