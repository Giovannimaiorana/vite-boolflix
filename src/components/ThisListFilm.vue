<script>
import { store } from '../store.js';
import ThisFilm from './ThisFilm.vue'
export default {
    name: 'ThisListFilm',
    components: {
        ThisFilm,
    },
    data() {
        return {
            store
        }
    }
}
</script>

<template>
    <h3 v-if="store.film.length > 0">Lista film</h3>
    <div class="containerFilm" v-for="element in store.film ">
        <ThisFilm :titolo="element.title" :OrTitle="element.original_title" :language="element.original_language"
            :vote="Math.floor(element.vote_average / 2)" :immagine="element.poster_path" />
    </div>
</template>

<style scoped lang="scss">
.containerFilm {
    display: flex;
    flex-wrap: wrap;
}
</style>