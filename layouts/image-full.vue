<script setup lang="ts">
import { computed } from 'vue'

const props = defineProps({
  image: {
    type: String,
    required: true,
  },
  caption: {
    type: String,
  }
})

const style = computed(() => ({
  backgroundImage: `url(${props.image})`,
  backgroundPosition: 'center',
  backgroundSize: 'cover',
}))
</script>

<template>
  <div class="slidev-layout image-full w-full h-full relative" :style="style">
    <div class="absolute inset-y-0 bottom-0 left-0 right-0 h-1/2 flex flex-col justify-end pb-12 px-14">
      <div class="z-10 text-center drop-shadow-lg">
        <slot />
        <div v-if="props.caption" class="mt-6 text-xl text-brand-primary font-mono tracking-widest uppercase font-bold drop-shadow-[0_2px_2px_rgba(0,0,0,0.8)]">
          {{ props.caption }}
        </div>
      </div>
    </div>
  </div>
</template>
