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
                        <div class="card">
                            <img :src="card.card_images[0].image_url" alt="#">
                            <p class="text-center fs-5">{{ card.name }}</p>
                            <p class="text-center">{{ card.archetype }}</p>
                        </div>

                    </div>
                </div>
            </div>
        </section>
    </main>
</template>

<style lang="scss" scoped>
main {
    background-color: bisque;
    padding-top: 1rem;
}

.card {
    background-color: coral;

    img {
        align-self: center;
        width: 90%;
    }
}
</style>