<script>
import { store } from '../store.js';
import axios from 'axios';

export default {
    data() {
        return {
            store,
            cardsList: [],
        }
    },
    methods: {
        getCard() {
            axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=10&offset=0 ', {
                params: {
                    ID: 12345
                }
            })
                .then((response) => {
                    console.log(response.data.data);
                    this.cardsList = response.data.data;
                })
                .catch(function (error) {
                    console.log(error);
                })
                .finally(function () {
                    // always executed
                });
        }
    },

    created() {
        this.getCard()
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