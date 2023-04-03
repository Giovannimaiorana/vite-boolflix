<script>
import { store } from '../store.js'
export default {
    name: 'ThisInfoJumbo',
    data() {
        return {
            store
        }
    }
}
</script>

<template>
    <div class="containerHeader">

        <div class="containerLogo">
            <img src="/logo.png" alt="">
            <ul>
                <li>Home</li>

                <li @click="$emit('trendingfilm')">Nuovi e Popolari</li>
                <li @click="$emit('allfilm')">In uscita</li>


            </ul>
        </div>
        <div class="containerSearch">
            <input type="text" placeholder="Cerca Film" v-model="store.search" @keyup.enter="$emit('searchText')">
            <button @click="$emit('searchText')"><i class="fa-solid fa-magnifying-glass"></i></button>

        </div>

        <div class="containerinfo">
            <div class="logotext">
                <img src="/logosearch.png" alt="">
                <img src="/textfx.png" alt="">
            </div>
            <div>
                <p>Diretto da William Malone, agli effetti speciali di questo film troviamo i fratelli Skotak che
                    lavoreranno al sequel di Alien. L’equipaggio della Shenandoah arriva su Titan, una luna di Saturno, per
                    esaminare dei misteriosi oggetti forse di origine aliena. Lì scoprono che i tedeschi hanno già mandato
                    una loro astronave, ma quando chiedono aiuto dopo un brutto atterraggio trovano l’equipaggio tedesco
                    massacrato da una creatura antica appena risvegliatasi.</p>
            </div>
            <div class="containerbutton">
                <button> Riproduci</button>
                <button>Altre Info </button>

            </div>
        </div>
    </div>
</template>

<style scoped lang="scss">
.containerinfo {
    width: 700px;

    position: absolute;
    left: 20px;
    top: 150px;

    .logotext {
        display: flex;
        align-items: center;
        margin-bottom: 10px;
    }


    p {
        font-size: 20px;
        font-weight: bolder;
    }

    img {
        width: 70px;
        margin-right: 10px;

    }

    .containerbutton {
        button {
            border-radius: 5px;
            border: none;
            width: 150px;
            height: 40px;
            margin-top: 30px;
            margin-right: 20px
        }
    }
}

.containerHeader {

    display: flex;
    justify-content: space-between;
    align-items: flex-start;
    background-image: url(/jumbotron.jpg);
    background-size: cover;
    height: 500px;



    .containerLogo {
        margin-top: 20px;
        display: flex;

        ul {
            list-style: none;
            display: flex;
            align-items: center;
            margin-left: 10px;

            li {
                margin-left: 20px;
                color: white;
                cursor: pointer;
            }

            li:hover {
                color: black;
            }
        }


        img {
            width: 200px;
            margin-left: 20px;
        }


    }




    .containerSearch {
        margin-right: 20px;
        margin-top: 20px;

        input {
            width: 200px;
            height: 30px;
            background-color: black;
            border: 1px solid grey;
            margin-right: 20px;
            padding: 10px;
            color: grey;
        }

        button {
            cursor: pointer;
            width: 50px;
            height: 30px;
            background-color: black;
            color: grey;
            border: 1px solid grey;
        }
    }
}
</style>