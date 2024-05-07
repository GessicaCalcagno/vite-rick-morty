<script>
import { store } from "../store.js";
export default {
  data() {
    return {
      store,
      statusArray: ["All", "Alive", "Dead", "unknown"],
    };
  },
};
</script>

<template>
  <div class="container py-4">
    <div class="d-flex justify-content-between">
      <div>
        <select @change="$emit('filter')" v-model="store.selectedStatus">
          <option :value="status" v-for="status in statusArray">
            {{ status }}
          </option>
        </select>
      </div>

      <!-- <p>Mostrati {{ cardsArray[0].length }}elementi</p> -->
    </div>
  </div>
</template>
<style scoped lang="scss"></style>
