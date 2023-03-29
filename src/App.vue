<script>
import AppMain from "./components/AppMain.vue";
import AppLoader from "./components/AppLoader.vue";
import {store} from "./store.js";

export default {
  data() {
    return {
      store,
    }
  },

  components: {
    AppMain,
    AppLoader,
  },

}
</script>


<template>

  <AppLoader v-if="!store.cards.length > 0"></AppLoader>

  <AppMain></AppMain>

</template>


<style lang="scss" scoped>

</style>