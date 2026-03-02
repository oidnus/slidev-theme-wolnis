<script setup lang="ts">
</script>

<template>
  <div class="grid grid-cols-5 w-full h-full">
    <!-- Teoria (2/5 szerokości) -->
    <div class="slidev-layout col-span-2 block pt-16 pl-14 pr-8 text-left">
      <slot name="left" />
    </div>
    
    <!-- Kod / Praktyka (3/5 szerokości) czysty widok -->
    <div class="slidev-layout col-span-3 block p-8 pt-16 text-left">
        <div class="w-full max-w-full overflow-auto syntax-container">
            <slot name="right" />
        </div>
    </div>
  </div>
</template>

<style scoped>
.syntax-container :deep(pre) {
    margin: 0;
    padding: 1.5rem !important;
    background: transparent !important;
}
.syntax-container :deep(.slidev-code-wrapper) {
    background: transparent !important;
}
</style>
