<script setup lang="ts">
</script>

<template>
  <div class="slidev-layout timeline h-full flex flex-col justify-center px-14">
    <div class="mb-14 w-full text-center">
      <slot name="header" />
    </div>
    
    <div class="flex flex-row justify-between items-start w-full relative pt-4">
      <!-- Pasek z tyłu na osi czasu -->
      <div class="absolute top-[2rem] left-8 right-8 h-1 bg-brand-primary opacity-30 z-0"></div>
      
      <!-- Krok 1 -->
      <div class="flex-1 px-4 text-center z-10 relative">
        <div class="w-16 h-16 bg-brand-primary rounded-full mx-auto mb-6 border-[6px] border-[#09090B] flex items-center justify-center text-white font-bold text-2xl shadow-lg shadow-brand-primary/20">1</div>
        <slot name="step1" />
      </div>
      
      <!-- Krok 2 -->
      <div class="flex-1 px-4 text-center z-10 relative">
        <div class="w-16 h-16 bg-[#7c3aed] rounded-full mx-auto mb-6 border-[6px] border-[#09090B] flex items-center justify-center text-white font-bold text-2xl shadow-lg shadow-[#7c3aed]/20">2</div>
        <slot name="step2" />
      </div>
      
      <!-- Krok 3 -->
      <div class="flex-1 px-4 text-center z-10 relative">
        <div class="w-16 h-16 bg-[#8b5cf6] rounded-full mx-auto mb-6 border-[6px] border-[#09090B] flex items-center justify-center text-white font-bold text-2xl shadow-lg shadow-[#8b5cf6]/20">3</div>
        <slot name="step3" />
      </div>
    </div>
    
    <div class="mt-14 w-full text-center">
      <slot />
    </div>
  </div>
</template>
