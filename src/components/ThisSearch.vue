<script>
import axios from 'axios';
import { store } from '../store.js'
import ThisInfoJumbo from './ThisInfoJumbo.vue';
export default {
    name: 'ThisSearch',
    data() {
        return {
            store
        }
    },
    components: {
        ThisInfoJumbo,
    },

}
</script>

<template>
    <ThisInfoJumbo />
</template>

<style lang="scss"></style>