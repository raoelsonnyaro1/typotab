<template>
  <table>
    <th></th>
    <tr v-for="(content, index) in contentTab" :key="index">
      <td>{{ content.id }}</td>
      <td>{{ content.value }}</td>
    </tr>
  </table>
</template>
<script>
export default {
  name: "TabComponent",
  props: {
    contentTab: {
      type: Array,
      default: () => [],
    },
  },
};
</script>