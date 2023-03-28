<script>
import {store} from "../store.js"
import axios from "axios";
import CardsItem from "./CardsItem.vue";

export default {
    data() {
        return {
            store,
        }
    },

    components: {
        CardsItem,
    },

    created() {

        axios.get("https://db.ygoprodeck.com/api/v7/cardinfo.php?num=50&offset=0").then((res) => {

            console.log(res.data.data);
            this.store.cards = res.data.data;
            console.log(this.store.cards)

        });

    },

}
</script>

<template>

    <div v-if="store.cards.length < 50" class="loading">Caricamento...</div>

    <div v-else class="cards-list">

        <CardsItem v-for="card in store.cards" :card="card"></CardsItem>
        
    </div>

</template>

<style lang="scss" scoped>
    .cards-list {
        display: flex;
        flex-flow: row wrap;
        justify-content: center;
        align-items: center;
        gap: 30px;
        margin: 30px;
    }

    .loading {
        position: absolute;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);

        font-size: 50px;
        padding: 8px 50px;
        border-radius: 30px;
        background-color: rgba(0, 0, 255, 0.336);

    }

</style>