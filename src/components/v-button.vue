<template>
  <div>
    <button
      class="
        text-xl
        outline outline-violet-700
        text-dark-900
        px-4
        py-2
        bg-violet-600
        rounded-2
        active:outline-violet-400
      "
      @click="sendInfo($event)"
    >
      {{ name }}
    </button>
  </div>
</template>

<script>
export default {
  props: ["name"],
  data() {
    return {};
  },
  methods: {
    sendInfo(event) {
      this.$emit("clicked", event);
    },
  },
};
</script>

<style>
</style>