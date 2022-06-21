<template>
  <div class="absolute" v-if="active">
    <img class="" src="../assets/flag-01.svg" alt="" />
    <div
      class="
        absolute
        top-0
        w-full
        h-[88%]
        flex
        justify-center
        items-center
        mx-auto
        brightness-100
        hover:brightness-125 hover:cursor-pointer
        transition-all
        ease-in-out
        duration-150
      "
      @click="toggleBookMark"
    >
      <h1 class="text-white text-2xl blur-sm">🟢</h1>
    </div>
  </div>
  <div class="absolute cursor-pointer" v-else>
    <img class="" src="../assets/flag-deactive.svg" alt="" />
  </div>
</template>

<script>
export default {
  props: ["active"],
  methods: {
    toggleBookMark(event) {
      this.$emit("toggleBookMark", event);
    },
  },
};
</script>

<style>
</style>