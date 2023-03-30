<script>
export default {
    data() {
        return {

        }
    },
}
</script>


<template>
    <div class="loading">
        
        Caricamento...

    </div>
</template>


<style lang="scss" scoped>
    
    .loading {
        position: fixed;
        top: 0;
        left: 0;

        display: flex;
        justify-content: center;
        align-items: center;

        width: 100vw;
        height: 100vh;

        font-size: 50px;
        padding: 8px 50px;
        background-color: black;
    }

</style>
