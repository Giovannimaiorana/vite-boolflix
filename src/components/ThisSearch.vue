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
        </div>
        <div class="containerSearch">
            <input type="text" placeholder="Cerca Film" v-model="store.search">
            <button @click="$emit('searchText')"><i class="fa-solid fa-magnifying-glass"></i></button>

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

    .containerLogo {
        margin-top: 20px;

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