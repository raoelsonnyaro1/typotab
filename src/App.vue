<template>
  <div id="app">
    <base-typo :bigTitle="bigTitle" :sub-title="subTitle" />
    <span v-if="isLoading"> loading... </span>
    <tab-component v-else :title="titleTableau" :content-tab="backValue" />
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
      titleTableau: "Tableau",
      backValue: [],
      bigTitle: "titre",
      subTitle: "sous-titre",
    };
  },

  methods: {
    async changeValue() {
      await setTimeout(() => {
        this.backValue = [{ id: 1, value: "firstvalue" }];
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
