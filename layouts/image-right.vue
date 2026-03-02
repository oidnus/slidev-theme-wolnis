<script setup lang="ts">
import { computed } from 'vue'

const props = defineProps({
  image: {
    type: String,
    required: true,
  },
  class: {
    type: String,
  },
})

const style = computed(() => ({
  backgroundImage: `url(${props.image})`,
  backgroundPosition: 'center',
  backgroundSize: 'cover',
}))
</script>

<template>
  <div class="grid grid-cols-2 w-full h-full bg-[#09090B]">
    <div class="slidev-layout col-span-1 block pt-16 px-14" :class="props.class">
      <slot />
    </div>
    <div class="col-span-1 w-full h-full relative" :style="style">
    </div>
  </div>
</template>
