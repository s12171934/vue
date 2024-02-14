<template>
  <div class="hello">
    <h1 :style="`color :${color}`" v-for="color in colors" :key="color">안녕</h1>
    <h1 v-for="nation in nations" :key="nation">{{ nation }}</h1>
    <h1 v-for="(nation, idx) in nations" :key="idx">{{ idx }} {{ nation }}</h1>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  data() {
    return {
      message: "안녕",
      colors: ['red','blue','green'],
      nations: ['프랑스','영국','미국'],
    };
  },
  props: {
    msg: String,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
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
