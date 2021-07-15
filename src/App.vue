<template>
  <the-header title="Vue3 SummerCamp Week1" :results="results"></the-header>
  <card-pool :results="results"></card-pool>
</template>

<script>
import axios from "axios";

import TheHeader from "./components/TheHeader.vue";
import CardPool from "./components/CardPool.vue";

export default {
  components: {
    TheHeader,
    CardPool,
  },
  data() {
    return {
      results: null,
    };
  },
  methods: {
    refreshResults() {
      axios({
        method: "get",
        url: "https://randomuser.me/api/?results=9",
      })
        .then((response) => {
          this.results = response.data.results;
          // console.log(JSON.parse(JSON.stringify(this.results)));
        })
        .catch(function (error) {
          console.log(error);
        });
    },
  },
  provide() {
    return {
      refreshResults: this.refreshResults,
    };
  },

  mounted() {
    this.refreshResults();
  },
};
</script>

<style lang="scss">
body {
  margin: 0;
background-color: #f1f3f8;
  #app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    // margin-top: 60px;
  }
}
</style>
