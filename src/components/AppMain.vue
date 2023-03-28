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

    }


}
</script>

<template>

    <div class="cards-list">

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
</style>