<script>
export default{
  name: "AppHeader"
}
</script>

<template>
  <header class="d-flex align-items-center">
    <div class="logo">
      <img src="../assets/img/Yugioh_anime_logo.webp" alt="">
    </div>
    <h1>Yu-Gi-Oh Api</h1>
  </header> 
</template>

<style scoped lang="scss">
header{
  height: 80px;
  padding: 1rem;

  img{
    width: 50px;
    margin-right: 1rem;
  }
}
</style>
