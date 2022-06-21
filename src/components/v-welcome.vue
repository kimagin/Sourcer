<template>
  <main class="flex flex-col items-center justify-center h-full">
    <div
      class="
        h-120
        flex flex-col
        justify-end
        bg-emerald-700/20
        backdrop-blur-20
        w-full
        rounded-2
        mb-4
        max-w-102
      "
    >
      <div class="relative flex flex-col justify-between h-full">
        <div
          class="bg-violet-900/60 w-full h-10 rounded-t-2 -z-1 absolute"
        ></div>
        <h1 class="text-5 font-mono px-4 pt-1">:/ logs ></h1>
        <div
          v-if="Info.length < 1"
          class="flex justify-center items-center h-full"
        >
          <h1 class="text-6">
            ⚡
            <span class="font-thin font-italic text-6 opacity-40 tracking-wider"
              >no logs recorded...</span
            >
          </h1>
        </div>
        <div
          v-else
          class="
            scroller
            overflow-y-scroll
            max-w-100
            break-words
            h-full
            mt-4
            px-4
          "
        >
          <div
            v-for="(info, index) in Info"
            :key="info"
            class="
              text-5
              leading-7
              font-mono
              tracking-normal
              lowercase
              opacity-90
              flex
              items-start
              h-max
            "
          >
            <div class="flex flex-col w-max mr-2 pr-2">
              <div
                class="
                  text-emerald-100
                  bg-gradient-to-bl
                  from-emerald-500/30
                  to-lime-400/50
                  rounded-full
                  mt-4
                  px-2
                "
              >
                <h4 class="font-medium w-max text-sm">
                  {{ getTime(index) }}
                </h4>
              </div>
              <div class="text-emerald-100 rounded-full px-2">
                <h4 class="font-medium w-max text-sm">
                  {{ getDate(index) }}
                </h4>
              </div>
            </div>

            <div class="border-l border-l-light-100/30 pl-2 min-h-16">
              <h1 class="mt-3">
                {{ getLog(index) }}
              </h1>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="flex justify-center items-center space-x-4 w-102">
      <custom-input
        @emittedEvent="getValue"
        holder="enter your daily log..."
        class=""
      />
      <custom-button class="" name="Clear" @click="clicked"></custom-button>
    </div>
  </main>
</template>

<script>
import customInput from "./v-input.vue";
import customButton from "./v-button.vue";
export default {
  components: { customInput, customButton },
  data() {
    return {
      stored: "",
      default: "write something...",
      Info: [],
      newDate: "",
    };
  },
  methods: {
    getValue(value) {
      const time = new Date().toLocaleTimeString();
      const date = new Date().toLocaleDateString();
      this.Info.push({ val: value, timeStamp: time, dateStamp: date });
    },
    clicked() {
      this.Info = [];
    },
    getLog(index) {
      return this.Info[index].val;
    },
    getTime(index) {
      return `${this.Info[index].timeStamp}`;
    },
    getDate(index) {
      return `${this.Info[index].dateStamp}`;
    },
  },
};
</script>

<style>
.scroller {
  overflow-y: scroll;
  overscroll-behavior-y: contain;
  scroll-snap-type: y proximity;
}
</style>