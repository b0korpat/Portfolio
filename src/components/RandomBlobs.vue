<template>
  <div class="fixed inset-0 overflow-hidden pointer-events-none z-0">
    <div
        v-for="(blob, index) in blobs"
        :key="index"
        class="absolute rounded-full filter blur-3xl animate-blob"
        :class="`animation-delay-${blob.delay}`"
        :style="{
        width: `${blob.size}rem`,
        height: `${blob.size}rem`,
        top: `${blob.top}%`,
        left: `${blob.left}%`,
        backgroundColor: blob.color,
        opacity: blob.opacity
      }"
    ></div>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue';

const props = defineProps({
  count: {
    type: Number,
    default: 7
  },
  minSize: {
    type: Number,
    default: 15
  },
  maxSize: {
    type: Number,
    default: 30
  }
});

const colors = [
  'rgba(126, 34, 206, 0.2)',
  'rgba(79, 70, 229, 0.15)',
  'rgba(219, 39, 119, 0.1)',
  'rgba(124, 58, 237, 0.15)',
  'rgba(37, 99, 235, 0.1)'
];

const blobs = ref([]);

onMounted(() => {
  blobs.value = Array.from({ length: props.count }).map(() => {
    const size = Math.floor(Math.random() * (props.maxSize - props.minSize + 1) + props.minSize);
    const top = Math.random() * 100;
    const left = Math.random() * 100;
    const colorIndex = Math.floor(Math.random() * colors.length);
    const delay = Math.floor(Math.random() * 5000);
    const opacity = Math.random() * 0.15 + 0.05;

    return {
      size,
      top,
      left,
      color: colors[colorIndex],
      delay,
      opacity
    };
  });
});
</script>

<style scoped>
.animate-blob {
  animation: blob 20s infinite alternate;
}

@keyframes blob {
  0% {
    transform: translate(0, 0) scale(1);
  }
  33% {
    transform: translate(30px, -50px) scale(1.1);
  }
  66% {
    transform: translate(-20px, 20px) scale(0.9);
  }
  100% {
    transform: translate(0, 0) scale(1);
  }
}

.animation-delay-0 {
  animation-delay: 0ms;
}

.animation-delay-1000 {
  animation-delay: 1000ms;
}

.animation-delay-2000 {
  animation-delay: 2000ms;
}

.animation-delay-3000 {
  animation-delay: 3000ms;
}

.animation-delay-4000 {
  animation-delay: 4000ms;
}
</style>