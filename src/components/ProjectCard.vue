<template>
  <div class="group rounded-xl overflow-hidden flex flex-col bg-gradient-to-b from-gray-900/90 to-gray-900/70 backdrop-blur-sm border border-purple-800/40 shadow-lg hover:shadow-2xl hover:shadow-purple-500/30 transition-all duration-300 h-full">
    <div class="relative h-52 overflow-hidden">
      <img
          :src="project.image || '/project-placeholder.jpg'"
          :alt="project.title"
          class="w-full h-full object-cover transition-transform duration-500 group-hover:scale-110"
          @error="handleImageError"
      />

      <div class="absolute inset-0 bg-gradient-to-t from-gray-900 via-gray-900/70 to-transparent"></div>

      <div class="absolute bottom-0 left-0 right-0 p-5">
        <h3 class="text-2xl font-bold text-white text-shadow">{{ project.title }}</h3>
      </div>
    </div>

    <div class="p-6 flex-1 flex flex-col">
      <p class="text-gray-300 mb-5">{{ project.description }}</p>

      <div class="flex flex-wrap gap-2 mb-3">
        <span
            v-for="(tech, index) in project.tech"
            :key="index"
            class="px-2.5 py-1.5 text-xs font-medium bg-purple-900/40 text-purple-200 rounded-full border border-purple-700/30 transition-all duration-300 hover:bg-purple-900/60"
        >
          {{ tech }}
        </span>
      </div>

      <div class="mt-auto pt-4 border-t border-purple-800/30">
        <div class="flex gap-3">
          <a
              v-if="project.link"
              :href="project.link"
              target="_blank"
              rel="noopener noreferrer"
              :class="[
        'inline-flex items-center justify-center py-3 px-4 rounded-lg bg-gradient-to-r from-purple-800/40 to-fuchsia-800/40 hover:from-purple-800/60 hover:to-fuchsia-800/60 text-purple-200 transition-all duration-300',
        project.github ? 'flex-1' : 'w-full'
      ]"
          >
            <span>View Project</span>
            <i class="bi bi-arrow-right ml-2 transition-transform duration-300 group-hover:translate-x-2"></i>
          </a>

          <a
              v-else-if="project.github"
              :href="project.github"
              target="_blank"
              rel="noopener noreferrer"
              class="w-full inline-flex items-center justify-center py-3 px-4 rounded-lg bg-gradient-to-r from-purple-800/40 to-fuchsia-800/40 hover:from-purple-800/60 hover:to-fuchsia-800/60 text-purple-200 transition-all duration-300"
          >
            <span>Visit GitHub</span>
            <i class="bi bi-github ml-2"></i>
          </a>

          <a
              v-if="project.link && project.github"
              :href="project.github"
              target="_blank"
              rel="noopener noreferrer"
              class="inline-flex items-center justify-center py-3 px-4 rounded-lg bg-gray-800/60 hover:bg-gray-800/80 text-purple-200 border border-purple-700/30 transition-all duration-300"
              title="View GitHub Repository"
          >
            <i class="bi bi-github text-lg"></i>
          </a>
        </div>
      </div>
  </div>
  </div>
</template>

<script setup>
const props = defineProps({
  project: {
    type: Object,
    required: true
  }
});

function handleImageError(e) {
  e.target.src = '/project-placeholder.jpg';
}
</script>

<style scoped>
.text-shadow {
  text-shadow: 0 2px 4px rgba(0, 0, 0, 0.5);
}
</style>