<script>
  import axios from 'axios';
  import { store } from './store';
  import AppHeader from './components/AppHeader.vue';
  import AppMain from './components/AppMain.vue';
  import Filter from './components/Filter.vue';



  export default{
    components: {
      AppHeader,
      AppMain,
      Filter,
    },
    data() {
      return {
        store
      };
    },
    methods: {
      
      getCardsFromApi(){
      let apiUrl = 'https://db.ygoprodeck.com/api/v7/cardinfo.php';
      let queryParams = {
        num: '20',
        offset: '0',
      };
      if (store.searchedArchetype !== ''){
        queryParams.archetype = store.searchedArchetype
      }
        // Prende le card dall'API e popola nello store
        axios.get(apiUrl, {params: queryParams})
        .then((response) => {
          store.cardsInfo = response.data.data;
        });
      },
      getArchetypesFromApi(){
        // Prende gli archetipi e popola l'array nello store
        axios.get('https://db.ygoprodeck.com/api/v7/archetypes.php')
        .then((response) =>{
          store.archetypes = response.data
        })
      },

    },
    mounted(){
      this.getArchetypesFromApi();
      this.getCardsFromApi();
    }
  }
</script>

<template>
  <div class="bg">
    <AppHeader></AppHeader>
    <Filter @archetypeSelected="getCardsFromApi"></Filter>
    <main>
      <AppMain></AppMain>
    </main>
  </div>
</template>

<style lang="scss">
  @use './style/generic.scss';

  .bg{
    background-image: url(https://images-wixmp-ed30a86b8c4ca887773594c2.wixmp.com/f/3ad5f1e1-a7ea-43d2-aeab-7ae5cc9aee62/d47ia5q-efb252bb-48ef-400b-988a-594dc7539006.png?token=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJ1cm46YXBwOjdlMGQxODg5ODIyNjQzNzNhNWYwZDQxNWVhMGQyNmUwIiwiaXNzIjoidXJuOmFwcDo3ZTBkMTg4OTgyMjY0MzczYTVmMGQ0MTVlYTBkMjZlMCIsIm9iaiI6W1t7InBhdGgiOiJcL2ZcLzNhZDVmMWUxLWE3ZWEtNDNkMi1hZWFiLTdhZTVjYzlhZWU2MlwvZDQ3aWE1cS1lZmIyNTJiYi00OGVmLTQwMGItOTg4YS01OTRkYzc1MzkwMDYucG5nIn1dXSwiYXVkIjpbInVybjpzZXJ2aWNlOmZpbGUuZG93bmxvYWQiXX0.blRPPb6MeqwRpjFJjSEj8xBoPcldJukLeqpVbgMrIp4);
    padding-bottom: 50px;
  }
</style>
