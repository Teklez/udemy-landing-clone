<template>
  <div class="w-full border-b">
    <HeadlessDisclosure
      v-for="(section, index) in dummyItems"
      :key="index"
      as="div"
      v-model="open[index]"
    >
      <HeadlessDisclosureButton
        class="w-full flex justify-between items-center py-4 px-2 bg-gray-100 hover:bg-gray-200 focus:outline-none"
      >
        <span class="font-bold">{{ title }}</span>
        <span class="hidden md:inline">
          {{ sectionLectures }} lectures •
          {{ Math.round(sectionLength / 60) }} min
        </span>
        <ChevronDownIcon
          :class="{ 'transform rotate-180': open[index] }"
          class="w-5 h-5 text-gray-700"
        />
      </HeadlessDisclosureButton>

      <HeadlessDisclosurePanel
        v-show="open[index]"
        class="px-2 pt-2 pb-4 border-t border-gray-200"
      >
        <div
          v-for="(item, idx) in section.items"
          :key="idx"
          class="flex items-center py-2"
        >
          <span
            :class="itemIconClass(item.content_summary)"
            class="pr-2 text-lg"
          ></span>
          <span
            :class="
              item.can_be_previewed
                ? 'underline text-indigo-600 cursor-pointer'
                : ''
            "
            >{{ item.title }}</span
          >
          <span
            v-if="item.can_be_previewed"
            class="ml-auto text-indigo-600 underline cursor-pointer hover:text-indigo-800"
            >Preview</span
          >
          <span class="hidden md:inline text-gray-500 ml-4">{{
            item.content_summary
          }}</span>
        </div>
      </HeadlessDisclosurePanel>
    </HeadlessDisclosure>
  </div>
</template>

<script>
import { ref } from "vue";
import {
  Disclosure as HeadlessDisclosure,
  DisclosureButton as HeadlessDisclosureButton,
  DisclosurePanel as HeadlessDisclosurePanel,
} from "@headlessui/vue";
import { ChevronDownIcon } from "@heroicons/vue/outline";

export default {
  name: "CourseSection",
  components: {
    HeadlessDisclosure,
    HeadlessDisclosureButton,
    HeadlessDisclosurePanel,
    ChevronDownIcon,
  },
  props: {
    title: {
      type: String,
      default: "Course Section Title",
    },
    sectionLectures: {
      type: Number,
      default: 10,
    },
    sectionLength: {
      type: Number,
      default: 300,
    },
  },
  setup() {
    const open = ref([true, false, false, false]); // First disclosure is open by default

    // Dummy data
    const dummyItems = [
      {
        title: "Introduction to Course",
        content_summary: "3 pages",
        can_be_previewed: true,
        items: [
          {
            title: "Introduction",
            content_summary: "3 pages",
            can_be_previewed: true,
          },
        ],
      },
      {
        title: "Lecture 1: Basics",
        content_summary: "10 min",
        can_be_previewed: false,
        items: [
          {
            title: "Basics Overview",
            content_summary: "5 min",
            can_be_previewed: false,
          },
        ],
      },
      {
        title: "Lecture 2: Advanced Topics",
        content_summary: "15 min",
        can_be_previewed: true,
        items: [
          {
            title: "Advanced Discussion",
            content_summary: "10 min",
            can_be_previewed: true,
          },
        ],
      },
      {
        title: "Conclusion and Summary",
        content_summary: "2 pages",
        can_be_previewed: false,
        items: [
          {
            title: "Final Thoughts",
            content_summary: "2 pages",
            can_be_previewed: false,
          },
        ],
      },
    ];

    const itemIconClass = (summary) => {
      return summary.includes("page")
        ? "fa-regular fa-file"
        : "fa-solid fa-circle-play";
    };

    return {
      open,
      dummyItems,
      itemIconClass,
    };
  },
};
</script>
