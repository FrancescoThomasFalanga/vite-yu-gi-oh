<script>
import {store} from "../store.js"
import axios from "axios";
import CardsItem from "./CardsItem.vue";
import AppSearchCard from "./AppSearchCard.vue";

export default {
    data() {
        return {
            store,
        }
    },

    components: {
        CardsItem,
        AppSearchCard,
    },

    created() {

        axios.get(this.store.APIcall).then((res) => {

            console.log(res.data.data);
            this.store.cards = res.data.data;
            console.log(this.store.cards);

        });

    },

    methods: {
        search() {

            let newApiString = this.store.APIcall;

            if (!this.store.archetypeName == "") {

                newApiString += `${this.store.APIquery}${this.store.archetypeName}`;
                
            };

            axios.get(newApiString).then((res) => {

                this.store.cards = res.data.data;

            });

        }
    },

}
</script>

<template>

    <AppSearchCard @searchArchetype="search()"></AppSearchCard>

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
        max-width: 1200px;
        margin: 30px auto;
        background-color: rgba(0, 0, 255, 0.178);
        padding: 20px;
        border-radius: 20px;
    }

</style>