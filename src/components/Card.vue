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
        <div class="archetype">{{ cardInfo.archetype }}</div>
    </div>
</template>

<style scoped lang="scss">
@use '../style/partials/variables.scss' as *;

.card{
    display: flex;
    flex-direction: column;
    justify-content: space-evenly;
    gap: 5px;
    width: calc((100% / 5) - 25px);
    text-align: center;
    font-weight: bolder;
    font-size: 12px;
    color: white;
    margin-bottom: 20px;
    border-radius: 10px;
    white-space:nowrap;
    height: max-content;

    .archetype{
        color: #57e9d0;
    }

    img{
        height: 100%;
        width: 100%;
    }
}

</style>