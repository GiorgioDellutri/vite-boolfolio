<script>
import AppMain from './components/AppMain.vue';

export default {
  name: 'App',
  components: {
    AppMain,
  },
  data() {
    return {
      // dati del componente 
    }
  }
}
</script>

<template>
  <main>
    <AppMain />
  </main>
</template>

<style lang="scss">
@use './styles/general.scss' as *;
@use 'node_modules/bootstrap/scss/bootstrap' as *;

.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}

.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
</style>
