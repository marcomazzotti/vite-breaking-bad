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
    axios.get(store.apiURL).then((resp) => {
      this.store.cards = resp.data.data;
    })
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