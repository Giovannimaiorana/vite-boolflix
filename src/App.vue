<script >
import ThisSearch from './components/ThisSearch.vue';
import ThisList from './components/ThisList.vue'
import { store } from './store.js'
import axios from 'axios';

export default {
  components: {
    ThisSearch,
    ThisList,
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
    <ThisList />
  </main>
</template>

<style ></style>
