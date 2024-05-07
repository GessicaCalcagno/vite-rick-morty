<script>
import axios from "axios";
import { store } from "./store";
import AppHeader from "./components/AppHeader.vue";
import CardList from "./components/CardList.vue";
import AppSearch from "./components/AppSearch.vue";

export default {
  components: {
    AppHeader,
    AppSearch,
    CardList,
  },
  data() {
    return {
      //store che punta su store
      store,
      isLoading: false,
    };
  },
  created() {
    this.getCards();
  },
  methods: {
    getCards() {
      this.isLoading = true;

      // Costuriamo i parametri per la chiamata axios
      const paramsObj = {};

      if (this.store.selectedStatus !== "All") {
        paramsObj.status = this.store.selectedStatus;
      }

      console.log("Get cards", this.store.selectedStatus);
      axios
        .get("https://rickandmortyapi.com/api/character", {
          params: paramsObj,
        })
        .then((resp) => {
          //salvo i dati all'interno della variabile store in store.js dell'array inizializzato vuoto cardList
          this.store.cardList = resp.data.results;
          this.isLoading = false;
        });
    },
  },
};
</script>
<template>
  <AppHeader />
  <AppSearch @filter="getCards" />
  <div v-if="isLoading">
    <h1 class="text-center">is loading ...</h1>
  </div>
  <CardList v-else />
</template>

<style lang="scss">
/* Sfondo grigio con righe e colonne bianche */
body {
  background-image: linear-gradient(to right, white 20px, transparent 15px),
    linear-gradient(to bottom, white 20px, transparent 15px);
  background-size: 50px 50px;
  background-color: #f5f5f5;
}
</style>
