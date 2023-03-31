<script>
export default {
    name: 'ThisFilm',
    props: {
        titolo: String,
        OrTitle: String,
        OrLang: String,
        vote: Number,
    }
}
</script>

<template>
    <div class="containerCardFilm">
        <h1>{{ titolo }}</h1> <!--Titolo -->
        <h2>{{ OrTitle }}</h2><!--Titolo Originale -->
        <h3>{{ OrLang }}</h3><!--Lingua originale -->
        <h5> {{ vote }}</h5><!--Voto -->
    </div>
</template>

<style scoped lang="scss">
.containerCardFilm {
    width: 200px;

}
</style>