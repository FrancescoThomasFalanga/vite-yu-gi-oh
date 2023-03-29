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
    
            <input type="text" placeholder="Cerca per archetipo" @keyup.enter="$emit('searchArchetype')" v-model="store.archetypeName">
            <button @click="$emit('searchArchetype')">Cerca</button>
    
        </div>
    </div>


</template>


<style lang="scss" scoped>
    .container {
        max-width: 1200px;
        margin: 30px auto;

        .search {
            padding: 40px 20px;
            background-color: rgba(0, 0, 255, 0.178);
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
        }
    }

</style>