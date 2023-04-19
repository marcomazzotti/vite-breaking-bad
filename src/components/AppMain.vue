<script>
import axios from "axios";
import {store} from "../store";
import AppCards from "./AppCards.vue";
import AppFilter from "./AppFilter.vue";
export default {
  name: "AppMain",
  components: { AppCards, AppFilter },
  data() {
    return {
      store
    };
  },
  mounted() {
    this.getCards();
  },
  methods: {
    getCards() {
      const params = {};
      if (this.store.selectedArchetype) {
        params.archetype = this.store.selectedArchetype
      }
      axios.get(this.store.apiURL, {
        params
      }).then((resp) => {
        console.log(resp);
        this.store.cards = resp.data.data
      })
    },
    handleFilter() {
      this.getCards();
    }
  }
}
</script>

<template>
  <main>
    <AppFilter @filter="handleFilter" />
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