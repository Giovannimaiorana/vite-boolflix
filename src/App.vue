<script >
import ThisSearch from './components/ThisSearch.vue';
import ThisListFilm from './components/ThisListFilm.vue'
import ThisListSeries from './components/ThisListSeries.vue';
import { store } from './store.js'
import axios from 'axios';

export default {
  components: {
    ThisSearch,
    ThisListFilm,
    ThisListSeries,
  },
  data() {
    return {
      store,
    }

  },
  methods: {
    generalListFilmSeries() {
      let generalApi = 'https://api.themoviedb.org/3/search'
      let filmApi = generalApi + '/movie?api_key=f15f93ea472c6620277f22eb5179fd0d';
      let seriesApi = generalApi + '/tv?api_key=f15f93ea472c6620277f22eb5179fd0d';
      if (store.search.length > 0) {
        filmApi += `&query=${store.search}`;
        seriesApi += `&query=${store.search}`;

        axios.get(filmApi)
          .then(response => {
            this.store.film = response.data.results;
          }),
          axios.get(seriesApi)
            .then(response => {
              this.store.serie = response.data.results;
            })
      }
    }
  }
}

</script>

<template>
  <header>
    <ThisSearch @searchText="generalListFilmSeries()" />
  </header>

  <main>
    <ThisListFilm />
    <h1>SerieTv</h1>
    <ThisListSeries />
  </main>
</template>

<style scoped lang="scss">
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
</style>
