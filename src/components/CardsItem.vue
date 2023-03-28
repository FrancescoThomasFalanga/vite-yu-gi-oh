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
                <strong>Nome Carta: </strong> 
                <span>{{card.name}}</span>
            </div>
            <div>
                <strong>Tipo Carta: </strong>
                <span>{{card.type}}</span>
            </div>

            <div v-for="price in card.card_prices">
                <strong>Prezzo Amazon: </strong>
                <span>{{price.amazon_price}} $</span>
            </div>


        </div>

</template>


<style lang="scss" scoped>
    


    .card {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        width: calc(100% / 5 - 30px);
        gap: 6px;
        padding-bottom: 15px;
        background-color: #51556c3f;

        border-left: 2px solid white;
        border-right: 2px solid white;
        border-bottom: 2px solid white;
        border-radius: 5px;
        box-shadow: 2px 3px 8px white;

        img {
            width: 100%;
            border-radius: 5px;
        }

        strong {
            text-transform: uppercase;
            font-size: 14px;
        }

        span {
            background-color: rgba(0, 0, 0, 0.377);
            border-radius: 10px;
            padding: 2px 4px;
            box-shadow: 2px 1px 2px rgba(0, 235, 235, 0.521);
        }

        hr {
            margin-top: 15px;
            width: 100%;
        }
    }



</style>