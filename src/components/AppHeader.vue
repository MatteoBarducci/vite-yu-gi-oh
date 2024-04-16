<script>
    export default{
        name: 'AppHeader',
    }
</script>

<template>
    <header>
        <img src="https://vignette1.wikia.nocookie.net/yugiohenespanol/images/a/aa/Yugioh_anime_logo.jpg/revision/latest?cb=20130310042737&path-prefix=es" alt="Yu-gi-oh logo">
    </header>
</template>

<style scoped lang="scss">
@use '../style/partials/variables.scss' as *;

header{
    display: flex;
    justify-content: center;
}

img{
    height: 70px;
}

    
</style>