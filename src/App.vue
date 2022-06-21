<template>
  <div
    class="
      relative
      flex flex-col
      items-center
      justify-center
      h-full
      overflow-hidden
    "
  >
    <div
      class="absolute top-10 left-14 flex items-center w-full max-w-400 h-max"
    >
      <h1 class="text-light-100 text-7 text-center">📃</h1>
      <h1 class="text-light-200 text-7 opacity-80 h-10 ml-4 font-normal">
        Log Manager
      </h1>
      <h1 class="h-3 text-violet-400/70 ml-2">v 0.1.2</h1>
    </div>
    <img
      class="
        absolute
        object-cover
        w-full
        h-full
        scale-105
        rotate-180
        opacity-95
        brightness-40
        -z-1
        hue-rotate-280
        mix-blend-luminosity
      "
      src="https://images.unsplash.com/photo-1637952112301-6090dca83ccb?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=2070&q=80"
      alt=""
    />

    <div class="mt-20">
      <v-welcome class="z-10 text-light-100"></v-welcome>
    </div>
  </div>
</template>

<script>
import vWelcome from "./components/v-welcome.vue";

export default {
  components: { vWelcome },
};
</script>

<style>
</style>