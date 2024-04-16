<script>
    import { store } from '../store';

    export default{
        name: 'Filter',
        data() {
            return{
                store
            }
        },
    }
</script>

<template>
    <div class="main-container">
        <select v-model="store.searchedArchetype" @change="$emit('archetypeSelected')">
            <option value="">Scegli un archetipo</option>
            <option v-for="archetype in store.archetypes" :value="archetype.archetype_name">{{ archetype.archetype_name }}</option>
        </select>
    </div>
    
</template>

<style scoped lang="scss">
@use '../style/partials/variables.scss' as *;

.main-container{
    display: flex;
    justify-content: center;
    margin-bottom: 20px;

    select{
        padding: 10px 14px;
    }
}

</style>