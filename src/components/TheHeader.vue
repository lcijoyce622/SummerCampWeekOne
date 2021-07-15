<template>
  <div class="title">
    <h1>{{ title }}</h1>
    <button class="container" type="button" @click="refreshResults">
      Refresh
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
   font-family: 'Noto Sans TC', sans-serif ;
    box-shadow: 0px 0px 0px 2px #d4f1ff;
    background: linear-gradient(to bottom, #0688fa 5%, #2dabf9 100%);
    background-color: #2dabf9;
    border-radius: 10px;
    border: none;
    display: inline-block;
    cursor: pointer;
    color: #ffffff;
    // font-family: Arial;
    font-size: 19px;
    padding: 12px 37px;
    margin: 1rem 0 0 0;
    text-decoration: none;
    text-shadow: 0px 1px 0px #263666;
  }
  button:hover {
     background: linear-gradient(to bottom, #2dabf9 5%, #0688fa 100%);
    background-color: #0688fa;
    box-shadow:  0 0.25rem 0.75rem rgba(94, 93, 93, 0.438);
  }
  button:active {
    position: relative;
    top: 1px;
  }
}
</style>