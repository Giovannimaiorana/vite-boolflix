<script>
import { store } from '../store.js'
export default {
    name: 'ThisSearch',
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
                <li>Serie Tv</li>
                <li>Film</li>
                <li>Nuovi e Popolari</li>
                <li>La Mia Lista</li>
                <li>Sfoglia per Lingua</li>

            </ul>
        </div>
        <div class="containerSearch">
            <input type="text" placeholder="Cerca Film" v-model="store.search">
            <button @click="$emit('searchText')"><i class="fa-solid fa-magnifying-glass"></i></button>

        </div>
        <div class="containerinfo">
            <div class="logotext">
                <img src="/logosearch.png" alt="">

            </div>
        </div>
    </div>
</template>

<style lang="scss">
.containerHeader {

    display: flex;
    justify-content: space-between;
    align-items: flex-start;
    background-image: url(/jumbotron.jpg);
    background-size: cover;
    height: 500px;

    .logotext {
        display: flex;
        align-items: center;
    }

    .containerinfo {
        width: 700px;
        height: 350px;
        position: absolute;
        left: 20px;
        top: 100px;
        border: 1px solid black;

        img {
            width: 60px;

        }
    }

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
            width: 50px;
            height: 30px;
            background-color: black;
            color: grey;
            border: 1px solid grey;
        }
    }
}
</style>