<template>
  <td>
    <slot />
  </td>
</template>

<style lang="postcss" scoped>
tbody td {
  @apply align-top first:pl-0 last:pr-0;
  padding: v-bind($dt('prose.tbody.td.padding'));
}
</style>
