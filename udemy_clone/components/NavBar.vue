<template>
  <nav class="flex items-center justify-between py-4 pr-6 shadow-md">
    <ul class="flex items-center space-x-6 list-none flex-grow">
      <li>
        <button type="button hidden" aria-label="menu-icon">
          <MenuOutlined class="text-white text-xl hidden" />
        </button>
      </li>
      <li class="">
        <NuxtLink to="/">
          <img
            src="https://www.udemy.com/staticx/udemy/images/v7/logo-udemy.svg"
            alt="udemy-logo"
            width="90"
            height="30"
          />
        </NuxtLink>
      </li>
      <li class="hidden md:block">
        <button
          type="button"
          aria-label="categories-button"
          class="text-gray-900"
        >
          Categories
        </button>
      </li>

      <!-- Search Bar Section -->
      <div class="flex-grow">
        <SearchBar />
      </div>    

      <li class="hidden lg:block">
        <button type="button" aria-label="udemy-business" class="text-gray-900">
          Udemy Business
        </button>
      </li>
      <li class="hidden lg:block">
        <button type="button" aria-label="teach-on-udemy" class="text-gray-900">
          Teach on Udemy
        </button>
      </li>
      <li class="hidden lg:block">
        <button type="button" aria-label="teach-on-udemy" class="text-gray-900">
          My learning
        </button>
      </li>

      <!-- Icons Section -->
      <li>
        <button type="button" aria-label="wishlist-button">
          <HeartOutlined class="text-gray-900 text-xl" />
        </button>
      </li>
      <li>
        <button type="button" aria-label="cart-button">
          <ShoppingCartOutlined class="text-gray-900 text-xl" />
        </button>
      </li>

      <li>
        <button type="button" aria-label="notification-button">
          <BellOutlined class="text-gray-900 text-xl" />
        </button>
      </li>
      <li>
        <button type="button" aria-label="profile-button">
          <img
            src="../static/profile.png"
            alt="profile-icon"
            width="32"
            height="32"
            class="rounded-full"
          />
        </button>
      </li>
    </ul>
  </nav>
</template>

<script>
import SearchBar from "./SearchBar.vue";
import {
  MenuOutlined,
  ShoppingCartOutlined,
  BellOutlined,
  HeartOutlined,
} from "@ant-design/icons-vue";

export default {
  components: {
    SearchBar,
    MenuOutlined,
    ShoppingCartOutlined,
    BellOutlined,
    HeartOutlined,
  },
};
</script>

<style scoped>
/* Custom class for navbar */
</style>
