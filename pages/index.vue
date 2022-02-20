<script setup lang="ts">
import {ref} from 'vue';

useMeta({
      title: 'Home Page'
    })

</script>


<template lang="pug">

.container
  .first
    Hero
  .second
   h1 lol

</template>


<style scoped lang="scss">

.container {
  overflow: auto;
  scroll-snap-type: y mandatory;
  height: 100vh;

  & > * {
    scroll-snap-align: center;
    height: 100vh;
  }
}


</style>