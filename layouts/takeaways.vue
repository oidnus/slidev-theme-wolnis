<script setup lang="ts">
</script>

<template>
  <div class="slidev-layout takeaways w-full h-full p-14 flex flex-col justify-center">
    
    <div class="mx-auto w-full max-w-4xl text-center mb-8 takeaways-header">
        <slot />
    </div>

    <div class="mx-auto w-full max-w-3xl takeaways-list">
        <slot name="list" />
    </div>

  </div>
</template>

<style scoped>
/* Podstawienie wszystkich kropek listy (ul li) na potężne purpurowe plusy/checki dla podsumowania (takeaways) */
.takeaways-list :deep(ul) {
    list-style: none !important;
    padding-left: 0;
    margin: 0;
}
.takeaways-list :deep(ul li) {
    position: relative;
    padding-left: 1.8rem;
    margin-bottom: 1rem;
    font-size: 1.5rem;
    line-height: 1.4;
    color: #e4e4e7; /* zinc-200 */
}
.takeaways-list :deep(ul li:last-child) {
    margin-bottom: 0;
}
.takeaways-list :deep(ul li)::before {
    content: "✓";
    position: absolute;
    left: -0.4rem;
    top: -0.1rem;
    color: #7c3aed; /* brand-primary */
    font-weight: bold;
    font-size: 1.8rem;
}
</style>
