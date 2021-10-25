<template>
  <div
    @click="makeActive"
    :class="{ active: isActive }"
  >
    <p
      v-if="isFile"
      class="file"
    >
      {{ item.name }}
    </p>
    <p
      v-if="isLink"
      class="link"
    >
      {{ item.name }}
    </p>
  </div>

</template>

<script>
export default {
  name: "File",
  props: {
    item: {
      type: Object,
    },
  },
  data() {
    return {
      isActive: false,
    };
  },
  computed: {
    isFile() {
      return this.item.type === "file";
    },
    isLink() {
      return this.item.type === "link";
    },
  },
  methods: {
    makeActive() {
      this.isActive = true;
    },
  },
};
</script>

<style scoped>
p {
  margin: 3px 0;
  padding: 5px;
  width: 20rem;
  cursor: pointer;
}

.file {
  color: rgb(232, 241, 97);
}

.active .file {
  color: #fff;
  background-color: rgba(197, 211, 9, 0.5);
  border-radius: 7px;
}

.link {
  color: #fff;
  font-style: italic;
  text-decoration: underline;
}

.active .link {
  color: #233329;
  background-color: #81da8c;
  border-radius: 7px;
}
</style>