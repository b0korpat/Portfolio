<template>
  <a
      :href="href"
      target="_blank"
      rel="noopener noreferrer"
      class="flex items-center p-4 rounded-lg bg-gray-800/50 hover:bg-gray-800 transition-all duration-300 group"
  >
    <div class="w-12 h-12 rounded-full bg-purple-800/30 flex items-center justify-center mr-4 group-hover:bg-purple-800/50 transition-colors duration-300">
      <i :class="['bi', icon, 'text-purple-400 text-xl']"></i>
    </div>
    <div>
      <p class="text-gray-400 text-sm mb-1">{{ label }}</p>
      <p class="text-gray-200">{{ value }}</p>
    </div>
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
  },
  label: {
    type: String,
    required: true
  },
  value: {
    type: String,
    required: true
  }
})
</script>