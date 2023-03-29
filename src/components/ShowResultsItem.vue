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
    <div class="generated">
        
        Sono state generate: {{ store.cards.length }} carte

    </div>
</template>


<style lang="scss" scoped>
    
.generated {
    font-size: 24px;
    font-weight: bold;
    background-color: #000f66a2;
}

</style>