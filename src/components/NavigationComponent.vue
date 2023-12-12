<template>
  <div class="navigation-component">
    <ul class="nav-links">
      <li><router-link to="/">Home</router-link></li>
      <li><router-link to="/contact">Contact</router-link></li>
      <li><router-link to="/api">API</router-link></li>
      <li><router-link to="/autre">Autre</router-link></li>
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

.nav-links>li {
  display: inline-block;
}

.nav-links>li+li {
  margin-left: 30px;
}
</style>