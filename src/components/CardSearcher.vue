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
            <option value="">New Delhi</option>
            <option value="">Istanbul</option>
            <option value="">Jakarta</option>
        </select>
    </div>
</template>

<style lang="scss" scoped>

</style>