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


            star: '',
        }
    },
    methods: {
        languageFlag() {
            if (this.language == 'en') {
                return '<img class="bandiera" src="/enghFlag.jpg" alt="en">';
            } else if (this.language == 'it') {
                return '<img class="bandiera"  src="/itaFlag.jpg" alt="it">';
            } else {
                return this.language;
            }
        },
        getImg() {
            let generalImg = 'https://image.tmdb.org/t/p/w342';
            return generalImg + this.immagine;

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

        this.getValutation();
    }
}
</script>

<template>
    <div class="containerCardFilm">

        <div class="cardFront">
            <div><img :src="getImg()"></div>
            <div class="cardBack">
                <h3>{{ titolo }}</h3> <!--Titolo -->
                <h4>{{ OrTitle }}</h4><!--Titolo Originale -->
                <span v-html="languageFlag()"></span>
                <h6 v-html="star"></h6><!--Voto -->
            </div>
            <div>

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

        display: flex;
        justify-content: center;
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