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
    <h3 v-if="store.serie.length > 0">Lista Serie</h3>
    <div class="containerContentSerie">
        <div class="containerSerie" v-for="(element, i ) in store.serie" :key="i">
            <ThisFilm :titolo="element.name" :OrTitle="element.original_name" :language="element.original_language"
                :vote="element.vote_average" :immagine="element.backdrop_path" />
        </div>
    </div>
</template>

<style scoped lang="scss">
.containerContentSerie {
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
    max-width: 90%;

    .containerSerie {
        margin: 20px;
    }
}
</style>