<template>
  <div class="bg-gray-900/60 backdrop-blur-sm border border-purple-800/30 rounded-xl p-6 hover:shadow-xl hover:shadow-purple-500/10 transition-all duration-500 group">
    <div class="flex items-center mb-6">
      <div class="w-10 h-10 rounded-full bg-purple-800/30 flex items-center justify-center mr-3">
        <i :class="['bi', icon, 'text-purple-400 text-xl']"></i>
      </div>
      <h3 class="text-xl font-semibold text-gray-200">{{ title }}</h3>
    </div>

    <div class="space-y-3">
      <slot></slot>
    </div>
  </div>
</template>

<script setup>
defineProps({
  title: {
    type: String,
    required: true
  },
  icon: {
    type: String,
    required: true
  }
})
</script>