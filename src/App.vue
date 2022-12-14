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
      axios
        .get(store.apiUrl)
        .then(res => {
          store.characterList = res.data.results
        })
        .catch(err => {
          console.log("Errori, err")
        })
    }
  },
  mounted() {
    getCharacters()
  }
}

</script>

<template>
  <AppHeader />
  <AppMain />

</template>

<style lang="scss">
@use "./components/style/general.scss";
</style>
