<script>
import axios from "axios";
import AppFilter from "./components/AppFilter.vue";
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import {store} from "./store";

export default{
    components: { AppHeader, AppMain, AppFilter },
    data(){
      return{
        store
      }
  },
    mounted() {
    this.getCards();
  },
  methods: {
    getCards(){
      const params = {};
      if(this.store.selectedArchetype){
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
      this.getCards
    }
  }
}
</script>

<template>
  <AppHeader />
  <AppMain />
</template>

<style lang="scss">
@use "./styles/general.scss"
</style>