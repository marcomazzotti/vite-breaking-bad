<script>
export default {
  name: "AppCards",
  props: {
    card: Object
  }
}
</script>

<template>
 <div class="card text-center">
  <img :src="card.card_images[0].image_url_small" alt="">
  <div class="card-body">
    <h5 class="card-title">{{ card.name }}</h5>
    <p class="card-text"> {{ card.archetype }}</p>
  </div>
 </div>
</template>

<style scoped lang="scss">
@use "../styles/partials/variables" as *;

.card{
  background-color: $bg-color;
}
</style>