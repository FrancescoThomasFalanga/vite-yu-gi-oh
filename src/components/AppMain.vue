<script>
import {store} from "../store.js"
import axios from "axios";
import CardsItem from "./CardsItem.vue";
import AppSearchCard from "./AppSearchCard.vue";
import ShowResultsItem from "./ShowResultsItem.vue";

export default {
    data() {
        return {
            store,
        }
    },

    components: {
        CardsItem,
        AppSearchCard,
        ShowResultsItem,
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

            }).catch(function (error) {
                if (error.response) {
                    alert("Stai Inserendo un Valore che non esiste");
                };
            })
        }
    },

}
</script>

<template>

    <AppSearchCard @searchArchetype="search()"></AppSearchCard>

    <ShowResultsItem class="flex"></ShowResultsItem>
    <div class="cards-list">


        <CardsItem v-for="card in store.cards" :card="card"></CardsItem>

    </div>
</template>

<style lang="scss" scoped>

    .flex {
        display: flex;
        max-width: 1200px;
        margin: 0 auto;
        padding: 20px;
        border-top-left-radius: 20px;
        border-top-right-radius: 20px;
    }
    .cards-list {
        display: flex;
        flex-flow: row wrap;
        align-items: center;
        max-width: 1200px;
        margin: 0 auto 30px;
        background-color: rgba(0, 0, 255, 0.178);
        padding: 20px;
        border-bottom-left-radius: 20px;
        border-bottom-right-radius: 20px;
    }

</style>