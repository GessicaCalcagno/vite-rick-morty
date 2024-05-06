<script>
import axios from "axios";

export default {
  data() {
    return {
      cardsArray: []
    };
  },
  created() {
    axios.get("https://rickandmortyapi.com/api/character", {

    }).then(resp => {
      console.log(resp);
      this.cardsArray = resp.data.results;
    });
  },
};
</script>
<template>
  <h1>Rick And Morty App</h1>
</template>
<style lang="scss"></style>
