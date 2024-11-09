<template>
    <div class="max-w-4xl mx-auto py-4">
      <p class="text-2xl font-extrabold mb-4">Course content</p>
      <section class="flex flex-wrap items-center mb-4">
        <p class="flex-grow text-base">
          {{ sections.length }} sections • {{ numOfLectures }} lectures •
          {{ timeInHours }}h {{ remainingMinutes }}m total length
        </p>
      </section>
      <ul>
        <li
          v-for="(section, idx) in sections"
          :key="idx"
          class="border-b border-gray-200"
        >
          <!-- Only the first section is expanded -->
          <CourseSection :expand="idx === 0" :sectionDetails="section" :idx="idx" />
        </li>
      </ul>
    </div>
  </template>
  
  <script setup>
  import { ref } from 'vue';
  import CourseSection from '~/components/CourseSection.vue';
  
  // Dummy data for the sections
  const details = {
    curriculum_context: {
      data: {
        sections: [
          { title: "Introduction to Course", content: "Learn the basics..." },
          { title: "Basic Concepts", content: "Understand foundational concepts..." },
          { title: "Advanced Techniques", content: "Explore advanced techniques..." },
          // Add more sections if needed
        ],
        num_of_published_lectures: 25,
        estimated_content_length_in_seconds: 5400,
      },
    },
  };
  
  // Extracting data from the dummy course details
  const { sections, num_of_published_lectures: numOfLectures, estimated_content_length_in_seconds: timeInSeconds } = details.curriculum_context.data;
  
  // Calculate the total time in hours and minutes
  const timeInHours = Math.floor(timeInSeconds / 3600);
  const remainingMinutes = Math.round((timeInSeconds % 3600) / 60);
  </script>
  
  <style scoped>
  /* Optional styling for icons */
  @import url("https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css");
  </style>
  