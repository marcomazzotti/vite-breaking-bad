<script>
import {store} from "../store";
import AppCards from "./AppCards.vue"
export default {
  name: "AppMain",
  components: { AppCards },
  data() {
    return {
      store
    };
  }
}
</script>

<template>
  <main>
    <div class="container">
      <div class="row row-cols-5">
        <div class="col mt-2 mb-2" v-for="card in store.cards">
          <AppCards :card="card" />
        </div>
      </div>
    </div>
  </main>
  
</template>

<style scoped lang="scss">
@use "../styles/partials/variables" as *;

  main{
    background-color: $bg-color;
    padding: 4rem 0 0 0;

    .container{
      background-color: white;
      padding: 2rem;
    }
  }
</style>