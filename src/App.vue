<script >
import ThisSearch from './components/ThisSearch.vue';
import ThisListFilm from './components/ThisListFilm.vue'
import ThisListSeries from './components/ThisListSeries.vue';
import ThisTrandingFilm from './components/ThisTrendingFilm.vue'
import { store } from './store.js'
import axios from 'axios';

export default {
  components: {
    ThisSearch,
    ThisListFilm,
    ThisListSeries,
    ThisTrandingFilm,
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
    },
    getTrandingFilm() {
      let generalApi = 'https://api.themoviedb.org/3/trending';
      let filmTrending = generalApi += '/movie/week?api_key=f15f93ea472c6620277f22eb5179fd0d';
      axios.get(filmTrending)
        .then(response => {
          this.store.trendingFilm = response.data.results;
        })

    }
  }
}

</script>

<template>
  <header>
    <ThisSearch @searchText="generalListFilmSeries()" @trendingfilm="getTrandingFilm()" />
  </header>

  <main>
    <div class="containerMain">
      <ThisTrandingFilm />
      <ThisListFilm />
      <ThisListSeries />
    </div>

  </main>
</template>

<style  lang="scss">
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
}

body {
  background-color: black;
}
</style>
