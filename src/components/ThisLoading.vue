<script>
import { store } from '../store.js';
export default {
    name: 'ThisLoading',
    data() {
        return {
            store
        }
    }
}
</script>

<template>
    <div class="load" v-if="store.loading">
        <img src="/logo.png" alt="">

    </div>
</template>

<style>
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
}
</style>