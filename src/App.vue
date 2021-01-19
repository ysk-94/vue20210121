<template>
  <AppHeader />
  <img alt="Vue logo" src="./assets/logo.png" />
  <HelloWorld msg="Hello Vue 3.0 + Vite" />
</template>

<style lang="scss">

</style>

<script>
import HelloWorld from './components/HelloWorld.vue';
import AppHeader from './components/AppHeader.vue';

export default {
  name: 'App',
  components: {
    HelloWorld,
    AppHeader
  }
}
</script>
