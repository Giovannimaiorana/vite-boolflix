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
    <div class="containerContentFilm">
        <div class="containerFilm" v-for="(element, i ) in store.film " :key="i">
            <ThisFilm :titolo="element.title" :OrTitle="element.original_title" :language="element.original_language"
                :vote="Math.floor(element.vote_average / 2)" :immagine="element.poster_path" />
        </div>
    </div>
</template>

<style scoped lang="scss">
.containerContentFilm {
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
    max-width: 90%;

}

.containerFilm {
    margin: 20px;
}
</style>