<script>
import axios from "axios";
import AppHeader from "./components/AppHeader.vue";

export default {
  components: {
    AppHeader,
  },
  data() {
    return {
      cardsArray: []
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
  <AppHeader />
</template>
<style lang="scss"></style>
