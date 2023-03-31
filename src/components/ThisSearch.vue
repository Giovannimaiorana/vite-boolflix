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
        <input type="text" placeholder="Cerca Film">
        <button>Search</button>

    </div>
</template>

<style></style>