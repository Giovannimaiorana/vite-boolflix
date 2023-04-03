<script>
import { store } from '../store.js';
export default {
    name: 'ThisLoading',
    data() {
        return {
            store
        }

    },
    mounted() {
        setTimeout(this.firstload, 1000);
        this.store.loading = true
    }

}

</script>

<template>
    <div class="load" v-if="store.loading">
        <img src="/logo.png" alt="">

    </div>
</template>

<style scoped lang="scss">
.load {
    background-color: black;
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    display: flex;
    justify-content: center;
    align-items: center;

    img {
        width: 600px;
        animation-name: animationBoolflix;
        animation-duration: 0.5s;
    }
}

@keyframes animationBoolflix {
    0% {
        width: 100px;
    }

    10% {
        width: 150px;
    }

    25% {
        width: 200px;
    }

    35% {
        width: 250px;
    }

    50% {
        width: 350px;
    }

    60% {
        width: 500px;
    }

    65% {
        width: 550px;
    }

    70% {
        width: 600px;
    }

    75% {
        width: 650px;
    }

    80% {
        width: 700px;
    }

    85% {
        width: 750px;
    }

    90% {
        width: 1000px;
    }

    95% {
        width: 850px;
    }

    100% {
        width: 700px;
    }

}
</style>