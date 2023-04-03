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
        setTimeout(firstload => {
            this.store.loading = false
        }, 2000);

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

    5% {
        width: 125px;
    }

    10% {
        width: 150px;
    }

    15% {
        width: 200px;
    }

    20% {
        width: 250px;
    }

    25% {
        width: 300px;
    }

    30% {
        width: 350px;
    }

    35% {
        width: 400px;
    }

    40% {
        width: 450px;
    }

    45% {
        width: 500px;
    }

    50% {
        width: 550px;
    }

    55% {
        width: 600px;
    }

    60% {
        width: 650px;
    }

    65% {
        width: 700px;
    }

    70% {
        width: 750px;
    }

    75% {
        width: 800px;
    }

    80% {
        width: 850px;
    }

    85% {
        width: 900px;
    }

    90% {
        width: 850px;
    }

    95% {
        width: 800px;
    }

    100% {
        width: 700px;
    }

}
</style>