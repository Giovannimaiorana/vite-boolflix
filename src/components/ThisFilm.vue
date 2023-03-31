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
            star: '',
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

        },
        getValutation() {
            let none = 5;
            for (let i = 0; i < this.vote; i++) {
                none--
                this.star += '<i class="fa-solid fa-star "></i>';
            }
            for (let i = 0; i < none; i++) {
                this.star += '<i class="fa-regular fa-star "></i>';
            }
        }
    },
    created() {
        this.languageFlag();
        this.getImg();
        this.getValutation();
    }
}
</script>

<template>
    <div class="containerCardFilm">
        <div><img :src="imgApi"></div>
        <h3>{{ titolo }}</h3> <!--Titolo -->
        <h4>{{ OrTitle }}</h4><!--Titolo Originale -->
        <!--<span v-html="flag"></span>-->

        <h6 v-html="star"></h6><!--Voto -->
    </div>
</template>

<style scoped lang="scss">
.containerCardFilm {
    max-width: 350px;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    border: 2px solid black;
    padding: 10px;
    margin-bottom: 10px;
    border-radius: 20px;


}
</style>