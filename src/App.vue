<template>
  <AppHeader />
  <CardList />
</template>

<style lang="scss">
</style>

<script>
import AppHeader from './components/AppHeader.vue';
import CardList from './components/CardList.vue'

export default {
  name: 'App',
  components: {
    AppHeader,
    CardList
  }
}
</script>
