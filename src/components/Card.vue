<script>

    export default{
        name: 'Card',
        props: {
            cardInfo: Object
        } 
    }
</script>

<template>
    <div class="card">
        <div>
            <img :src="cardInfo.card_images[0].image_url">
        </div>
        <div>{{ cardInfo.name }}</div>
        <div>{{ cardInfo.archetype }}</div>
    </div>
</template>

<style scoped lang="scss">
@use '../style/partials/variables.scss' as *;

.card{
    display: flex;
    flex-direction: column;
    gap: 5px;
    width: calc((100% / 5) - 20px);
    text-align: center;
    font-weight: bolder;
    color: white;
    margin-bottom: 20px;
    border-radius: 10px;

    img{
        height: 100%;
        width: 100%;
    }
}

</style>