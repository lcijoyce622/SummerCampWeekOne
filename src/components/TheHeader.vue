<template>
  <div class="title">
    <h1>{{ title }}</h1>
    <button class="container" type="button" @click="refreshResults">
      換一批
    </button>
  </div>
</template>
<script>
// import axios from "axios";
export default {
  props: ["title"],
  inject: ["refreshResults"],
  data() {
    return {
      //  title:''
    };
  },
};
</script>
<style lang="scss" scoped>
.title {
  //   text-align: left;
  h1 {
    background-color: rgb(91, 208, 255);
    // text-align: center;
    padding: 2rem;
    margin: 0;
  }
  button {
    border: none;
    background-color: rgb(4, 78, 139);
    outline: none;
    border-radius: 10px;
    padding: 1rem;
    margin: 1rem 0 0 0;
    color: white;
    font-family: "Franklin Gothic Medium", "Arial Narrow", Arial, sans-serif;
  }
}
</style>