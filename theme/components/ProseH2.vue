<script setup lang="ts">
defineProps<{ id: string }>()
</script>

<template>
  <h2 :id="id">
    <NuxtLink :href="`#${id}`">
      <slot />
    </NuxtLink>
  </h2>
</template>

<style lang="postcss" scoped>
h2 {
  @apply text-gray-900 mt-8 mb-4 scroll-mt-[calc(var(--header-height)+4.5rem)] text-2xl font-semibold leading-snug tracking-tight sm:scroll-mt-[calc(var(--header-height)+2rem)];
}

h2 + * {
  @apply mt-0;
}

h2 > a {
  @apply relative;

  &:before {
    @apply absolute top-0 left-[2px] h-[calc(100%+2px)] w-[calc(100%-4px)] content-[''];
  }

  &:hover {
    &:before {
      @apply border-gray-900 border-b border-dashed;
    }
    &:after {
      @apply absolute -right-5 h-3 w-3;
      content: url("data:image/svg+xml;charset=utf-8,%3Csvg xmlns='http://www.w3.org/2000/svg' fill='none' viewBox='0 0 24 24' stroke='#000'%3E%3Cpath stroke-linecap='round' stroke-linejoin='round' stroke-width='2' d='M13.828 10.172a4 4 0 00-5.656 0l-4 4a4 4 0 105.656 5.656l1.102-1.101m-.758-4.899a4 4 0 005.656 0l4-4a4 4 0 00-5.656-5.656l-1.1 1.1'/%3E%3C/svg%3E");
    }
  }
}

.dark h2 > a:hover::after {
  content: url("data:image/svg+xml;charset=utf-8,%3Csvg xmlns='http://www.w3.org/2000/svg' fill='none' viewBox='0 0 24 24' stroke='#fff'%3E%3Cpath stroke-linecap='round' stroke-linejoin='round' stroke-width='2' d='M13.828 10.172a4 4 0 00-5.656 0l-4 4a4 4 0 105.656 5.656l1.102-1.101m-.758-4.899a4 4 0 005.656 0l4-4a4 4 0 00-5.656-5.656l-1.1 1.1'/%3E%3C/svg%3E");
}
</style>
