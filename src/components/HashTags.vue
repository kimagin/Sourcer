<template>
  <div>
    <ul class="flex space-x-[.2em] mt-6 justify-start tracking-wider">
      <li v-for="tag in tags" :key="tag" class="">
        <div
          class="
            bg-neutral-800
            hover:bg-emerald-400 hover:text-emerald-900 hover:cursor-pointer
            rounded-full
            transition-colors
            duration-150
            ease-in-out
            px-3
            py-[.05em]
          "
        >
          <p class="text-xs">{{ tag }}</p>
        </div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  props: ["tags"],
  data() {
    return {
      hashTags: ["books", "ideas", "Vue.js"],
    };
  },
};
</script>

<style scoped>
</style>