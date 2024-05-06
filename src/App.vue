<script>
import axios from "axios";
import AppHeader from "./components/AppHeader.vue";
import CardList from "./components/CardList.vue";

export default {
  components: {
    AppHeader,
    CardList,
  },
  data() {
    return {
      cardsArray: [],
    };
  },
  created() {
    axios.get("https://rickandmortyapi.com/api/character", {

    }).then((resp) => {
      console.log(resp);
      this.cardsArray = resp.data.results;
    });
  },
};
</script>
<template>
  <div id="app">
    <AppHeader />
    <CardList :cardsArray="cardsArray" />
  </div>
</template>
<style lang="scss">
/* Sfondo grigio con righe e colonne bianche */
body {
  background-image: linear-gradient(to right, white 20px, transparent 15px),
    linear-gradient(to bottom, white 20px, transparent 15px);
  background-size: 50px 50px;
  background-color: #F5F5F5;
}
</style>
