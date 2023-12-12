<template>
  <div class="home-div">
    <TextImageComponent />
    <TextImageComponent />
  </div>
</template>

<script>
  import TextImageComponent from '../components/TextImageComponent.vue';

  export default{
    components: {
      TextImageComponent
    }
  }
</script>

<style>
.home-div{
    display: flex;
    flex-direction: column;
    align-items: center;
}
</style>
