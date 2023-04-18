<script>
import {store} from "../store";
export default{
  name: "AppFilter",
  emits: ["filter"],
  data(){
    return{
      store,
      ArchetypeArray : ["Alien", "Ally of Justice", "Ancient Gear"]
    }
  }
}
</script>

<template>
  <div class="container">
    <select name="archetype" id="archetype" @change="$emit('filter')" v-model="store.selectedArchetype">
      <option value="">All</option>
      <option :value="archetype" v-for="archetype in ArchetypeArray">{{ archetype }}</option>
    </select>
  </div>
</template>

<style scoped lang="scss">
</style>