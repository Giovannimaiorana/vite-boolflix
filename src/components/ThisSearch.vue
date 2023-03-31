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
    <div class="containerSearch">
        <input type="text" placeholder="Cerca Film" v-model="store.search">
        <button @click="$emit('searchText')">Search</button>

    </div>
</template>

<style lang="scss"></style>