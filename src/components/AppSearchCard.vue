<script>
import {store} from "../store.js"

export default {
    data() {
        return {
            store,
        }
    },
}
</script>


<template>

    <div class="container">
        <div class="search">

            <div>
                <input type="text" placeholder="Cerca per archetipo" @keyup.enter="$emit('searchArchetype')" v-model="store.archetypeName">
                <button @click="$emit('searchArchetype')">Cerca</button>
            </div>
    

            <div>
                <strong>Yu-Gi-Oh! API</strong>
            </div>
    
        </div>
    </div>


</template>


<style lang="scss" scoped>
    .container {
        max-width: 1200px;
        margin: 30px auto;

        .search {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px 20px;
            background-color: #000f66a2;
            border-radius: 20px;

            input {
                padding: 8px;
                background-color: rgba(0, 0, 255, 0.733);
            }

            button {
                cursor: pointer;
                margin-left: 10px;
                padding: 8px;
                background-color: rgba(0, 0, 255, 0.733);

            }

            strong {
                font-size: 32px;
            }
        }
    }

</style>