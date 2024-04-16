<script>
    import Card from './Card.vue'

    export default{
        name: 'AppMain',
        components: {
            Card,
        },
        data() {
            return{
                
            }
        }, 
    }
</script>
<!-- https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0 -->
<template>
    <main>
        <div class="main-container">
            <div class="cards">
                <Card></Card>
                <Card></Card>
                <Card></Card>
                <Card></Card>

            </div>
        </div>
    </main>
</template>

<style scoped lang="scss">
@use '../style/partials/variables.scss' as *;

    main{
        background-image: url(https://images-wixmp-ed30a86b8c4ca887773594c2.wixmp.com/f/3ad5f1e1-a7ea-43d2-aeab-7ae5cc9aee62/d47ia5q-efb252bb-48ef-400b-988a-594dc7539006.png?token=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJ1cm46YXBwOjdlMGQxODg5ODIyNjQzNzNhNWYwZDQxNWVhMGQyNmUwIiwiaXNzIjoidXJuOmFwcDo3ZTBkMTg4OTgyMjY0MzczYTVmMGQ0MTVlYTBkMjZlMCIsIm9iaiI6W1t7InBhdGgiOiJcL2ZcLzNhZDVmMWUxLWE3ZWEtNDNkMi1hZWFiLTdhZTVjYzlhZWU2MlwvZDQ3aWE1cS1lZmIyNTJiYi00OGVmLTQwMGItOTg4YS01OTRkYzc1MzkwMDYucG5nIn1dXSwiYXVkIjpbInVybjpzZXJ2aWNlOmZpbGUuZG93bmxvYWQiXX0.blRPPb6MeqwRpjFJjSEj8xBoPcldJukLeqpVbgMrIp4);
    }
</style>