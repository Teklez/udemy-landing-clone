<template>
  <nav
    class="flex items-center justify-between py-4 px-6 bg-gray-800 shadow-md"
  >
    <ul class="flex items-center space-x-6 list-none" >
      <li>
        <button type="button" aria-label="menu-icon">
          <!-- <MenuOutlined class="text-white text-xl" />   -->
        </button>
      </li>
      <li class="flex-grow">
        <NuxtLink to="/Udemy-Clone-ReactJS/">
          <img
            src="https://www.udemy.com/staticx/udemy/images/v7/logo-udemy.svg"
            alt="udemy-logo"
            width="110"
            height="32"
          />    
        </NuxtLink>
      </li>
      <li class="hidden md:block">
        <button type="button" aria-label="categories-button" class="text-white">
          Categories
        </button>
      </li>
      <SearchBar />
      <li class="hidden md:block">
        <button type="button" aria-label="search-button">
          <SearchOutlined class="text-white text-xl" />
        </button>
      </li>
      <li class="hidden lg:block">
        <button type="button" aria-label="udemy-business" class="text-white">
          Udemy Business
        </button>
      </li>
      <li class="hidden lg:block">
        <button type="button" aria-label="teach-on-udemy" class="text-white">
          Teach on Udemy
        </button>
      </li>
      <li>
        <button type="button" aria-label="cart-button">
          <ShoppingCartOutlined class="text-white text-xl" />
        </button>
      </li>
      <li class="hidden md:block">
        <button
          type="button"
          aria-label="login-button"
          class="text-white border border-white rounded px-4 py-1"
        >
          Log in
        </button>
      </li>
      <li class="hidden md:block">
        <button
          type="button"
          aria-label="signup-button"
          class="bg-white text-gray-800 rounded px-4 py-1"
        >
          Sign up
        </button>
      </li>
      <li>
        <button type="button" aria-label="language-button">
          <GlobalOutlined class="text-white text-xl" />
        </button>
      </li>
    </ul>
  </nav>
</template>

<script>
import SearchBar from "./SearchBar.vue";
import {
  MenuOutlined,
  SearchOutlined,
  ShoppingCartOutlined,
  GlobalOutlined,
} from "@ant-design/icons-vue"; // Import Vue Icons

export default {
  components: {
    SearchBar,
    MenuOutlined,
    SearchOutlined,
    ShoppingCartOutlined,
    GlobalOutlined,
  },
};
</script>

<style scoped>
/* Custom class for navbar */
</style>
