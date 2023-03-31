<script>
import { store } from '../store'
import ThisFilm from './ThisFilm.vue';
export default {
    name: 'TheListSeries',
    components: {
        ThisFilm


    },
    data() {
        return {
            store
        }
    }
}
</script>

<template>
    <h3 v-if="store.serie.length > 0">Lista film</h3>
    <div class="containerSerie" v-for="element in store.serie">
        <ThisFilm :titolo="element.name" :OrTitle="element.original_name" :language="element.original_language"
            :vote="element.vote_average" :immagine="element.backdrop_path" />


    </div>
</template>

<style></style>