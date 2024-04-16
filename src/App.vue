<script>
  import axios from 'axios';
  import { store } from './store';
  import AppHeader from './components/AppHeader.vue';
  import AppMain from './components/AppMain.vue';


  export default{
    components: {
      AppHeader,
      AppMain
    },
    data() {
      return {
        store
      };
    },
    methods: {
      getCardsFromApi(){
        // Prende le card dall'API e popola nello store
        axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0')
        .then((response) => {
          store.cardsInfo = response.data.data;
        });
      }
    },
    mounted(){
      this.getCardsFromApi();
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
