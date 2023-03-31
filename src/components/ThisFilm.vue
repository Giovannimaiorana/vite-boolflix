<script>
export default {
    name: 'ThisFilm',
    props: {
        titolo: String,
        OrTitle: String,
        OrLang: String,
        vote: Number,
    },
    data() {
        return {
            flag: ''
        }
    },
    methods: {
        languageFlag() {
            if (this.OrLang == 'en') {
                this.flag = '<img src="/enghFlag.jpg"';
            } else if (this.OrLang == 'it') {
                this.flag = 'img src="/itaFlag.jpg"';
            } else {
                this.flag = this.OrLang;
            }
        }
    },
    created() {
        this.languageFlag;
    }
}
</script>

<template>
    <div class="containerCardFilm">
        <h1>{{ titolo }}</h1> <!--Titolo -->
        <h2>{{ OrTitle }}</h2><!--Titolo Originale -->
        <span v-html="flag"></span>
        <h5> {{ vote }}</h5><!--Voto -->
    </div>
</template>

<style scoped lang="scss">
.containerCardFilm {
    width: 200px;

}
</style>