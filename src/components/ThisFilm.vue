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
            let generalImg = 'https://image.tmdb.org/t/p/w300';
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

        <div class="cardFront">
            <div><img :src="imgApi"></div>
            <div class="cardBack">
                <h3>{{ titolo }}</h3> <!--Titolo -->
                <h4>{{ OrTitle }}</h4><!--Titolo Originale -->
                <!--<span v-html="flag"></span>-->

                <h6 v-html="star"></h6><!--Voto -->
            </div>
        </div>



    </div>
</template>

<style scoped lang="scss">
.containerCardFilm {
    max-width: 350px;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
    padding: 10px;
    margin-bottom: 10px;
    border-radius: 20px;
    --background: linear-gradient(to left, #fa0505 0%, #89282b 100%);
    padding: 5px;
    border-radius: 5px;
    overflow: visible;
    background: #f7ba2b;
    background: var(--background);
    position: relative;
    z-index: 1;

    .cardBack {
        position: absolute;
        top: 50%;
        width: 100%;
        display: flex;
        flex-direction: column;
        align-items: center;
        display: none;

    }

    .cardFront:hover .cardBack {
        display: flex;
        width: 350px;
    }

    .cardFront:hover {
        img {
            filter: opacity(30%);
        }
    }

    div {


        img {
            border-radius: 5px;
        }
    }
}
</style>