<template>
  <div class="hello">
    <h1 @mouseover="isRed = !isRed" :class="{ red: isRed }">{{ bigTitle }}</h1>
  </div>
</template>

<script>
export default {
  name: "BaseTypo",
  props: {
    bigTitle: String,
  },

  data() {
    return {
      isRed: false,
    };
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.red {
  color: red;
}
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
