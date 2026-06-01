<template>
  <div class="card">
    <h3>{{ title }}</h3>
    <p>{{ description }}</p>
    <div class="card-footer">
      <h4 class="stat">{{ stat }}</h4>
      <h4 class="label">{{ label }}</h4>
    </div>
  </div>
</template>

<script setup>
defineProps({
  title: { type: String, required: true },
  description: { type: String, required: true },
  stat: { type: String, required: true },
  label: { type: String, required: true }
})
</script>