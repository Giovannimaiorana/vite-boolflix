<script >
import ThisSearch from './components/ThisSearch.vue';
import { store } from './store.js'
import axios from 'axios';

export default {
  components: {
    ThisSearch,
  },
  data() {
    return {
      store,
    }

  },
}

</script>

<template>
  <header>
    <ThisSearch />
  </header>

  <main>

  </main>
</template>

<style ></style>
