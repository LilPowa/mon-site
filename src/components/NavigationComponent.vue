<template>
  <div class="navigation-component">
    <ul class="nav-links">
      <li><a href="#">Accueil</a></li>
      <li><a href="#">Contact</a></li>
      <li><a href="#">API</a></li>
      <li><a href="#">Autre</a></li>
    </ul>
  </div>
</template>

<script>
export default {
}
</script>

<style scoped>
.navigation-component {
  display: flex;
  justify-content: center;
}

.nav-links {
  list-style-type: none;
  margin: 0;
  padding: 0;
}

.nav-links > li {
  display: inline-block;
}

.nav-links > li + li {
  margin-left: 30px;
}
</style>