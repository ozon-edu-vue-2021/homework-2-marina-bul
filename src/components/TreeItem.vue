<template>
  <ul>
    <li
      v-for="(item, index) in items"
      :key="index"
    >
      <folder
        v-if="isFolder(item.type)"
        :folderItem="item"
      />
      <file
        v-else
        :item="item"
      />
    </li>
  </ul>
</template>

<script>
import Folder from "./Folder.vue";
import File from "./File.vue";
export default {
  name: "TreeItem",
  components: { Folder, File },
  props: {
    items: {
      type: Array,
    },
  },

  computed: {
    isFolder: function () {
      return (type) => type === "directory";
    },
  },
};
</script>

<style scoped>
</style>