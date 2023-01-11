<script>
import { store } from '../store.js';
import axios from 'axios';

export default {
    name: 'AppMain',
    data() {
        return {
            store,
            cardsList: [],
        }
    },
    methods: {
        getCard() {
            axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=12&offset=0 ', {
                params: {
                    ID: 12345
                }
            })
                .then((response) => {
                    console.log(response.data.data);
                    this.cardsList = response.data.data;
                    // console.log(response.data.data[0].card_images)
                })
                .catch(function (error) {
                    console.log(error);
                })
                .finally(function () {
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
                    <div class="col-4 mb-3" v-for="card in cardsList">
                        <img :src="card.card_images[0].image_url" alt="#">

                    </div>
                </div>
            </div>
        </section>
    </main>
</template>

<style lang="scss" scoped>

</style>