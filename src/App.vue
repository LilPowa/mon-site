<template>
  <nav>
    <NavigationComponent />
  </nav>
  <main>
    <RouterView />
  </main>
</template>

<script>
  import NavigationComponent from './components/NavigationComponent.vue';

  export default{
    components: {
      NavigationComponent,
    }
  }
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
}

nav a.router-link-exact-active {
  color: #42b983;
}
</style>
