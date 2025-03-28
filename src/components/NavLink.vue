<template>
  <a
    :href="href"
    class="flex items-center px-4 py-3 rounded-lg transition-colors duration-200 w-full"
    :class="isActive ? 'bg-purple-900/40 text-purple-300' : 'hover:bg-purple-900/20 text-gray-400 hover:text-purple-300'"
  >
    <i :class="['bi', icon, 'text-xl md:mr-4']"></i>
    <span class="px-4 md:block group-hover:block whitespace-nowrap">{{ label }}</span>
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
  isActive: {
    type: Boolean,
    default: false
  }
})
</script>