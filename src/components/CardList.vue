<script>
import { store } from "../store";
import AppCard from "./AppCard.vue";

export default {
  components: {
    AppCard,
  },
  data() {
    return {
      store,
    };
  },
};
</script>

<template>
  <div class="container">
    <div class="row row-cols-1 row-cols-md-2 row-cols-lg-4">
      <div class="col" v-for="card in store.cardList">
        <AppCard :cardObj="card" />
      </div>
    </div>
  </div>
</template>

<style scoped lang="scss"></style>
