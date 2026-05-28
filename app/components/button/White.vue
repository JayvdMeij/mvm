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

  color: var(--donker-blauw);
  background-color: var(--wit);
  padding: 8px 30px;
  transition: transform 0.2s ease-in-out;
  border-radius: 400px;

  &:hover {
    transform: translateY(-3px);
  }
}
</style>