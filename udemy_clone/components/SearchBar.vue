<template>
  <li
    class="flex-grow hidden md:flex items-center justify-center min-w-[20rem]"
  >
    <form
      @submit.prevent="searchPressed(barValue)"
      class="flex items-center w-full h-12 px-4 rounded-full bg-whitesmoke border border-black"
    >
      <button
        @click="searchPressed(barValue)"
        type="button"
        class="border-none bg-transparent min-w-[50px] flex justify-center items-center"
        aria-label="search-icon"
      >
        <!-- Use Vue Icon instead of Font Awesome -->
        <SearchOutlined class="text-gray-500 text-lg" />
      </button>
      <input
        v-model="barValue"
        @keydown.enter="keySearch"
        type="text"
        placeholder="Search for anything"
        class="w-full bg-transparent text-base outline-none border-none"
      />
    </form>
  </li>
</template>

<script>
import { SearchOutlined } from "@ant-design/icons-vue"; // Import Vue Icon

export default {
  components: {
    SearchOutlined, // Register the icon component
  },
  data() {
    return {
      barValue: "",
    };
  },
  methods: {
    searchPressed(barValue) {
      this.$router.push({
        path: "/Udemy-Clone-ReactJS/",
        query: barValue ? { filter: barValue } : {},
      });
    },
    keySearch(e) {
      if (e.key === "Enter") {
        e.preventDefault();
        this.searchPressed(this.barValue);
      }
    },
  },
};
</script>

<style scoped>
/* Add custom styles for things like background-color (whitesmoke) if needed */
.bg-whitesmoke {
  background-color: #f5f5f5;
}
</style>
