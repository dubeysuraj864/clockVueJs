<template>

    <realTimeClock />

</template>

<script>

import realTimeClock from './components/realTimeClock.vue'
export default {
  name: 'App',
  components: {
    realTimeClock
  }
 
}
</script>

<style>
#app {
  font-family: System-ui;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;

}

</style>
