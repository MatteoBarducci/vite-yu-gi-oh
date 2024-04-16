<script>
    export default{
        name: 'AppHeader',
    }
</script>

<template>
    <header>
        <img src="https://upload.wikimedia.org/wikipedia/commons/2/21/Yu-Gi-Oh%21.png" alt="Yu-gi-oh logo">
    </header>
</template>

<style scoped lang="scss">
@use '../style/partials/variables.scss' as *;

header{
    display: flex;
    justify-content: center;
    margin-bottom: 30px;
}

img{
    height: 90px;
}

    
</style>