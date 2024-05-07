<script>
export default {
  props: {
    cardObj: Object,
  },
};
</script>

<template>
  <div class="card">
    <img class="rounded-circle" :src="cardObj.image" alt="" />
    <div class="card-body">
      <h5 class="text-center">{{ cardObj.name }}</h5>
      <p class="text-center m-0">{{ cardObj.status }}</p>
      <p class="text-center">{{ cardObj.species }}</p>
    </div>
  </div>
</template>

<style scoped lang="scss">
.card {
  border: 0;
  background-color: transparent;
}
</style>
