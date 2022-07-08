<template>
  <div id="app">
    <base-typo msg="Welcome to my App" />
    <span v-if="isLoading"> loading... </span>
    <tab-component v-else :content-tab="backValue" />
  </div>
</template>

<script>
import BaseTypo from "./components/BaseTypo.vue";
import TabComponent from "./components/TabComponent.vue";

export default {
  name: "App",
  components: {
    BaseTypo,
    TabComponent,
  },
  data() {
    return {
      isLoading: true,
      backValue: [],
    };
  },

  methods: {
    async changeValue() {
      await setTimeout(() => {
        this.backValue = [{ id: 1, value: "kaiza" }];
        this.isLoading = false;
      }, 300);
    },
  },

  created() {
    this.changeValue();
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
