<template>
  <div class="text-image-component">
    <p>Vue.js est un framework JavaScript de base pour la création d'interfaces utilisateurs riches.</p>
    <img src="https://vuejs.org/images/logo.png" alt="Vue.js Logo">
  </div>
</template>

<script>
export default {
}
</script>

<style scoped>
.text-image-component {
  display: flex;
  padding-top: 20px;
  width: 70%;
  align-items: center;
}

img{
  width: 150px;

}
</style>