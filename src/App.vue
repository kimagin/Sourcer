<template>
  <ul>
    <li v-for="item in exportedResources" :key="item.id">
      <ResourceItem
        :isBookMarked="item.isBookMarked"
        @toggle-bookmark="changeStatus"
        :id="item.id"
        :title="item.title"
        :description="item.description"
        :tags="item.tags"
      ></ResourceItem>
    </li>
  </ul>
</template>

<script>
import ResourceItem from "./components/ResourceItem.vue";
export default {
  components: { ResourceItem },
  data() {
    return {
      exportedResources: [
        {
          id: "id1",
          title: "Official Guide",
          description:
            "The official Vue.js documentation. In order to solve most of problems that you are going to encounter during working with Vue, you can refer to this documentation",
          link: "https://vuejs.org",
          isBookMarked: false,
          tags: ["Vue.js", "frame work", "refrence", "dev"],
        },
        {
          id: "id2",
          title: "Tailwind CSS",
          description:
            "Tailwind CSS documentation.It has all the necessary syntaxes required for windy CSS and you can choose colors as well",
          link: "https://tailwindcss.com/docs/installation",
          isBookMarked: false,
          tags: ["books", "css", "front", "style"],
        },
        {
          id: "id3",
          title: "Blender",
          description: "Blender is a great program made for creating 3d models",
          link: "https://tailwindcss.com/docs/installation",
          isBookMarked: false,
          tags: ["3d", "object", "render"],
        },
      ],
    };
  },
  methods: {
    changeStatus(input) {
      const identifiedItem = this.exportedResources.find(
        (item) => item.id === input
      );
      identifiedItem.isBookMarked = !identifiedItem.isBookMarked;
    },
  },
};
</script>

<style>
</style>