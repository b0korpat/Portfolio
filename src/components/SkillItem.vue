<template>
  <div class="flex items-center py-2 px-3 rounded-lg bg-gray-800/50 hover:bg-gray-800 transition-colors duration-200">
    <i :class="[(icon.includes('bi ') ? icon : `bi ${icon}`), 'text-purple-400 mr-3']"></i>
    <span class="text-gray-300">{{ name }}</span>
  </div>
</template>

<script setup>
defineProps({
  name: {
    type: String,
    required: true
  },
  icon: {
    type: String,
    required: true
  }
})
</script>