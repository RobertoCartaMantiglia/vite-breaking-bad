<script>
import { store } from '../store.js';

export default {
    name: 'CardSearcher',
    data() {
        return {
            store,
        }
    }
}
</script>

<template>
    <div class="mb-3">
        <label for="" class="form-label">archetypes</label>
        <select class="form-select" @change="$emit('changeArchetype')" v-model="store.serchArchetype" name="" id="">
            <option selected>Select one</option>
            <option value="Alien">Alien</option>
            <option value="Laval">Laval</option>
            <option value="Inzektor">Inzektor</option>
            <option value="Umi">Umi</option>
            <option value="Gusto">Gusto</option>


        </select>
    </div>
</template>

<style lang="scss" scoped>

</style>