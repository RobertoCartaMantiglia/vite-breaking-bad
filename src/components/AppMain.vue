<script>
import { store } from '../store.js';

export default {
    data() {
        return {
            store,
        }
    },
}
</script>

<template>
    <main>
        <section>
            <div class="container">
                <div class="row">
                    <p>{{ store.serchText }}</p>
                </div>
            </div>
        </section>
    </main>
</template>

<style lang="scss" scoped>

</style>