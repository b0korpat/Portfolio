<template>
  <a
      :href="href"
      target="_blank"
      rel="noopener noreferrer"
      class="text-gray-400 hover:text-purple-300 transition-colors duration-200"
  >
    <i :class="['bi', icon, 'text-xl']"></i>
  </a>
</template>

<script setup>
defineProps({
  href: {
    type: String,
    required: true
  },
  icon: {
    type: String,
    required: true
  }
})
</script>