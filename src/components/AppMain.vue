<script>
    import { store } from '../store';
    import Card from './Card.vue'

    export default{
        name: 'AppMain',
        components: {
            Card,
        },
        data() {
            return{
                store
            }
        }, 
    }
</script>
<!-- https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0 -->
<template>
    <main>
        <div class="main-container">
            <div class="cards">
                <Card v-for="card in store.cardsInfo" :key="card.id" :cardInfo="card"></Card>
            </div>
        </div>
    </main>
</template>

<style scoped lang="scss">
@use '../style/partials/variables.scss' as *;

    main{
        .main-container{
            background-color: rgba(0, 0, 0, 0.496);
            padding: 35px;
            border-radius: 20px;
        }
        .cards{
            display: flex;
            justify-content: space-between;
            flex-wrap: wrap;
        }
    }
</style>