<script>
  import AppHeader from './components/AppHeader.vue';
  import AppMain from './components/AppMain.vue';


  export default{
    components: {
      AppHeader,
      AppMain
    }
  }
</script>

<template>
  <AppHeader></AppHeader>
  <main>
    <AppMain></AppMain>
  </main>
</template>

<style lang="scss">
  @use './style/generic.scss';
</style>
