<template>
    <div class="flex overflow-hidden">
      <div v-for="(page, index) in pages" :key="index" class="flex-1">
        <div class="flex items-center justify-between p-4 bg-gray-200 cursor-pointer" @click="togglePage(index)">
          <h3 class="text-lg font-medium">{{ page.title }}</h3>
          <span v-if="currentPage === index">-</span>
          <span v-else>+</span>
        </div>
        <div class="p-4" :class="{ 'w-0': currentPage !== index, 'w-full': currentPage === index }" @transitionend="onTransitionEnd">
          <slot :page="page"></slot>
        </div>
      </div>
    </div>
  </template>
  
  <script setup>
  import { ref, onMounted } from 'vue'
  
  const props = defineProps({
    pages: {
      type: Array,
      required: true
    }
  })
  
  const currentPage = ref(0)
  const isTransitioning = ref(false)
  
  function togglePage(index) {
    if (currentPage.value === index) {
      currentPage.value = -1
    } else {
      currentPage.value = index
    }
  }
  
  function onTransitionEnd() {
    isTransitioning.value = false
  }
  
  onMounted(() => {
    // Set the width of each page to the width of the container
    const container = document.querySelector('.page-accordion')
    const pages = container.querySelectorAll('.flex-1')
    pages.forEach(page => {
      page.style.width = `${container.clientWidth}px`
    })
  })
  </script>
  
  <style scoped>
  .cursor-pointer {
    cursor: pointer;
  }
  
  /* Transition styles */
  .p-4 {
    transition: width 0.3s ease-in-out;
  }
  .w-0 {
    width: 0;
    overflow: hidden;
  }
  </style>