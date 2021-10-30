<template>
  <div id="app">
    <h1>VUE FILE TREE</h1>
    <div class="tree-wrapper">
      <folder :folderItem="tree" />
    </div>

  </div>
</template>

<script>
import items from "../public/static/node_modules.json";
import Folder from "./components/Folder.vue";

export default {
  name: "App",
  components: {
    Folder,
  },

  data() {
    return {
      tree: items,
    };
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

#app {
  padding: 20px;
  min-height: 100vh;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  color: #fff;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  background-color: #63d471;
  background-image: linear-gradient(315deg, #63d471 0%, #233329 74%);
}

.tree-wrapper {
  margin-left: 10rem;
  width: 35rem;
}

h1 {
  margin-bottom: 30px;
  text-align: center;
}

ul {
  padding-left: 20px;
  list-style-type: none;
}
</style>
