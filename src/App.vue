<template>
  <div id="app">
    <NavigationComponent />
    <TextImageComponent />
  </div>
</template>

<script>
import NavigationComponent from './components/NavigationComponent.vue';
import TextImageComponent from './components/TextImageComponent.vue';

export default {
  components: {
    NavigationComponent,
    TextImageComponent,
  },
};
</script>