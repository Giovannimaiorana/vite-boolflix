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
        <ThisFilm :titolo="element.title" :OrTitle="element.original_title" :OrLang="element.original_language"
            :vote="element.vote_average" />
    </div>
</template>

<style scoped lang="scss">
.containerFilm {
    display: flex;
    flex-wrap: wrap;
}
</style>