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
            <img v-for="img in card.card_images" :src="img.image_url" alt="">

            <strong>Nome Carta: </strong> 
            <span>{{card.name}}</span>

            <strong>Tipo Carta: </strong>
            <span>{{card.type}}</span>

            <strong>Archetipo: </strong>
            <span v-if="card.archetype">{{card.archetype}}</span>
            <span v-else>Unknown</span>
    </div>
</template>


<style lang="scss" scoped>
    
    .card {
        text-align: center;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        gap: 6px;
        width: calc(100% / 5 - 30px);
        padding-bottom: 15px;
        margin: 15px;
        background-color: #000f66a2;
        border-radius: 5px;
        border-left: 2px solid white;
        border-right: 2px solid white;
        border-bottom: 2px solid white;
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
            font-size: 14px;
            background-color: rgba(0, 0, 0, 0.377);
            border-radius: 10px;
            padding: 2px 4px;
            box-shadow: 2px 1px 2px rgba(0, 235, 235, 0.521);
        }
    }

</style>