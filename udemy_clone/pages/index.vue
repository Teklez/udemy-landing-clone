<template>
  <div>
    <NavBar />
    <CourseHeader />
    <CourseObjectives />
    <ExploreRelatedTopics />
    <CourseContent/>
    <Footer/>
  </div>
</template>

<script>
import NavBar from "../components/NavBar.vue";
import CourseHeader from "~/components/CourseHeader.vue";
import CourseObjectives from "~/components/CourseObjectives.vue";
import ExploreRelatedTopics from "~/components/ExploreRelatedTopics.vue";
import CourseContent from "~/components/CourseContent.vue";
import Footer from "~/components/Footer.vue"
</script>
