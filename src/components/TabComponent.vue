<template>
  <div>
    <table class="mx-auto">
      <th colspan="3">{{ title }}</th>
      <tr v-for="(content, index) in contentTab" :key="index">
        <td>{{ content.id }}</td>
        <td>{{ content.value }}</td>
        <td>
          <input
            type="button"
            :value="btnSupprimer"
            @click.prevent="deleteValue(content)"
          />
        </td>
      </tr>
    </table>
    <input type="text" v-model="newItem" />
    <input type="button" :value="btnText" @click="addValue" />
  </div>
</template>
<script>
export default {
  name: "TabComponent",
  props: {
    contentTab: {
      type: Array,
      default: () => [],
    },
    btnText: {
      type: String,
      default: "add",
    },

    inputText: {
      type: String,
      default: "",
    },
    title: {
      type: String,
      default: "",
    },
    btnSupprimer: {
      type: String,
      default: "delete",
    },
  },

  data() {
    return {
      newItem: "",
    };
  },

  methods: {
    addValue() {
      if (this.newItem != "") {
        this.contentTab.push({
          id: this.contentTab.length + 1,
          value: this.newItem,
        });
        this.newItem = "";
      }
    },

    deleteValue(content) {
      this.contentTab = this.contentTab.filter((i) => i !== content);
    },
  },
};
</script>

<style scoped>
table {
  border-collapse: collapse;
}

th,
td {
  border: 1px solid black;
  padding: 10px;
}

.mx-auto {
  margin-left: auto;
  margin-right: auto;
}
input[type="button"] {
  background-color: black;
  border: none;
  color: white;
  padding: 0.5rem 1rem;
  text-decoration: none;
  cursor: pointer;
}
</style>