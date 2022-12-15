<script>
import axios from 'axios';
import AppHeader from './components/AppHeader.vue';
import AppMain from './components/AppMain.vue';
import { store } from './store';



export default {
  components: {
    AppHeader, AppMain,
  },
  data() {
    return {
      store,
    }
  },
  methods: {
    getCharacters() {

      let myUrl = store.apiUrl;

      if (store.apiSelectText === "alive" || store.apiSelectText === "dead" || store.apiSelectText === "unknown") {
        myUrl += `?${store.apiStatus}=${store.apiSelectText}`
      }

      axios
        .get(myUrl)
        .then(res => {
          store.characterList = res.data.results;
        })
        .catch(err => {
          console.log("Errori, err")
        })
    }
  },
  mounted() {
    this.getCharacters()
  }
}

</script>

<template>
  <AppHeader />
  <AppMain @search="getCharacters" />

</template>

<style lang="scss">
@use "./components/style/general.scss";
</style>
