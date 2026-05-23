<template>
  <a :href="href">
    <slot />
  </a>
</template>

<script setup>
defineProps({
  href: {
    type: String,
    required: true,
  }
})
</script>

<style scoped>
a {
  display: inline-block;
  color: var(--off-white-wit);
  background-color: var(--donker-blauw);
  padding: 24px 8px;
  transition: transform 0.2s ease-in-out;

  &:hover {
    transform: translateY(-3px);
  }
}
</style>