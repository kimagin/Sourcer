<template>
  <div class="container relative">
    <flag
      @click="toggleBookMark"
      class="absolute top-0 right-6 z-100 w-8"
      :active="isBookMarked"
    ></flag>
    <edit-button class="w-6 absolute bottom-5 right-6"> </edit-button>
    <div>
      <h1 class="text-7 text-warm-gray-100 tracking-normal font-normal">
        {{ title }}
      </h1>
    </div>
    <div class="flex text-gray-400/40 text-xs">
      <h4>23.05.2022</h4>
      <h4>10:16 AM</h4>
    </div>
    <div class="mt-6">
      <p class="text-sm leading-snug">
        {{ description }}
      </p>
    </div>
    <div class="mt-4">
      <a href="#" class="text-sm text-emerald-400">View Resource</a>
    </div>
    <tags :tags="tags"></tags>
  </div>
</template>

<script>
import flag from "./Flag.vue";
import editButton from "./EditButton.vue";
import tags from "./HashTags.vue";
export default {
  components: { flag, editButton, tags },
  props: ["isBookMarked", "id", "title", "description", "tags"],
  data() {
    return {};
  },
  methods: {
    toggleBookMark() {
      this.$emit("toggle-bookmark", this.id);
    },
  },
};
</script>

<style scoped>
.container {
  @apply text-warm-gray-400 flex flex-col w-100 from-[#3C3F45] to-[#2D3038]  bg-gradient-to-b rounded-2xl shadow-2xl shadow-black/60 py-6 pt-9 my-4 h-max px-8;
}
</style>