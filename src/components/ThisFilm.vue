<script>
export default {
    name: 'ThisFilm',
    props: {
        titolo: String,
        OrTitle: String,
        language: String,
        vote: Number,
        immagine: String,
    },
    data() {
        return {
            flag: '',
            imgApi: '',
        }
    },
    methods: {
        languageFlag() {
            if (this.language == 'en') {
                this.flag = '<img src="/enghFlag.jpg" alt="en">';
            } else if (this.language == 'it') {
                this.flag = '<img src="/itaFlag.jpg" alt="it">';
            } else {
                this.flag = this.language;
            }
        },
        getImg() {
            let generalImg = 'https://image.tmdb.org/t/p/w342';
            this.imgApi = generalImg + this.immagine;

        }
    },
    created() {
        this.languageFlag();
        this.getImg();
    }
}
</script>

<template>
    <div class="containerCardFilm">
        <div><img :src="imgApi"></div>
        <h1>{{ titolo }}</h1> <!--Titolo -->
        <h2>{{ OrTitle }}</h2><!--Titolo Originale -->
        <span v-html="flag"></span>
        <h5> {{ vote }}</h5><!--Voto -->
    </div>
</template>

<style scoped lang="scss">
.containerCardFilm {

    max-width: 500px;
    border: 2px solid black;
    padding: 10px;
}
</style>