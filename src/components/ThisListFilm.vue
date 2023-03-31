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
    <div class="containerFilm" v-for="element in store.film ">
        <ThisFilm :titolo="element.title" :OrTitle="element.original_title" :language="element.original_language"
            :vote="element.vote_average" :immagine="element.poster_path" />
    </div>
</template>

<style scoped lang="scss"></style>