<script>
export default {
    data() {
        return {
            
        }
    },

    props: {
        card: Object,
    },
}
</script>


<template>


        <div class="card">
            
            <div v-for="img in card.card_images">
                <img :src="img.image_url" alt="">
            </div>
    
            <div>
                Nome Carta: {{card.name}}
            </div>
            <div>
                Tipo Carta: {{card.type}}
            </div>

            <div v-for="price in card.card_prices">
                Prezzo su Amazon: {{ price.amazon_price }} $
            </div>

        </div>

</template>


<style lang="scss" scoped>
    


    .card {
        display: flex;
        flex-direction: column;
    }

    img {
        width: 300px;
        height: auto;
    }


</style>