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
import { SearchOutlined } from "@ant-design/icons-vue";

export default {
  components: {
    SearchOutlined,
  },
  data() {
    return {
      barValue: "",
    };
  },
};
</script>

<style scoped>
.bg-whitesmoke {
  background-color: #f5f5f5;
}
</style>
