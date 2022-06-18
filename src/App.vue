<template>
  <div id="app">
    <ButtonRipple />
  </div>
</template>

<script>
import ButtonRipple from './components/ButtonRipple.vue';

export default {
  name: 'App',
  components: {
    ButtonRipple,
  },
};
</script>

<style>
html {
  background: rgb(21, 24, 30);
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
