<template>
  <div class="border border-gray-300 p-6 max-w-3xl mx-auto mb-4">
    <p class="text-2xl font-extrabold mb-4">What you'll learn</p>
    <div class="grid grid-cols-2">
      <div
        v-for="(objective, index) in objectives"
        :key="index"
        class="flex items-center text-gray-700 w-full mb-2"
      >
        <i class="fa-solid fa-check mr-2 text-gray-500"></i>
        <p> {{ objective }}</p>
       
      </div>
    </div>
  </div>
</template>

<script setup>
const objectives = [
  "Learn to build React applications",
  "Understand the fundamentals of JavaScript",
  "Master the art of styling with Tailwind CSS",
  "Work with APIs and data fetching",
  "Gain hands-on experience with React hooks",
  "Understand component-based architecture",
];
</script>

<style scoped>
@import url("https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css");
</style>
