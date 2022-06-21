<template>
  <div class="text-xl">
    <input
      @keyup.enter="setValue($event)"
      v-model="name"
      :placeholder="holder"
      type="text"
      id="name"
      class="
        bg-dark-300
        py-3
        px-5
        placeholder:font-italic
        focus:outline-emerald-600 focus:outline-3 focus:bg-emerald-900
        outline-none outline-3 outline-dark-600
        rounded-md
      "
      autocomplete="off"
    />
  </div>
</template>

<script>
export default {
  props: ["Info", "holder"],
  data() {
    return {
      name: "",
    };
  },
  methods: {
    setValue(event) {
      // this.$emit("input", event);
      // this.name = event.target.value;
      this.$emit("emittedEvent", this.name);
      event.target.value = "";
    },
  },
};
</script>

<style>
</style>