<template>
  <div>
    <div
      @click="toggle"
      class="folder"
    >
      <span>{{ folderItem.name }}</span>
      <span class="icon">[{{ isOpened ? "-" : "+" }}]</span>
    </div>
    <tree-item
      :items="folderItem.contents"
      v-if="isOpened"
    />
  </div>
</template>

<script>
export default {
  name: "Folder",
  props: {
    folderItem: {
      type: Object,
    },
  },
  data() {
    return {
      isOpened: false,
    };
  },

  methods: {
    toggle() {
      this.isOpened = !this.isOpened;
    },
  },

  beforeCreate: function () {
    this.$options.components.TreeItem = require("./TreeItem.vue").default;
  },
};
</script>

<style scoped>
.folder {
  margin: 7px 0;
  font-size: 18px;
  font-weight: bold;
  cursor: pointer;
}
.icon {
  margin-left: 10px;
}
</style>