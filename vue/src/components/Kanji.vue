<template>

    <section class="section has-text-centered m-t-lg">
        <div class="columns">
            <div class="column">
                <h1 class="title is-size-1">{{kanji.ideogram}}</h1>
            </div>
        </div>

        <div class="columns is-multiline is-centered">
            <div class="column is-12 has-text-center">
                <p class="is-size-5">Kunyomi</p>
            </div>
            <div class="column is-5 has-text-center is-paddingless">
                <p class="is-size-5">
                    <span v-for="yomi in kanji.kunyomi" :key="yomi" class="p-l-sm p-r-sm">{{yomi}}</span>
                </p>
            </div>
        </div>

        <div class="columns is-multiline is-centered m-t-l">
            <div class="column is-12 has-text-center">
                <p class="is-size-5">Onyomi</p>
            </div>
            <div class="column is-5 has-text-center is-paddingless">
                <p class="is-size-5">
                    <span v-for="yomi in kanji.onyomi" :key="yomi" class="p-l-sm p-r-sm">{{yomi}}</span>
                </p>
            </div>
        </div>

        <div class="columns is-centered m-t-md m-b-sm">
            <div class="column is-2">
                <p>Partes</p> <span v-for="part in kanji.parts" :key="part" class="p-l-sm p-r-sm">{{part}}</span>
            </div>
            <div class="column is-2">
                <p>Radical</p> {{kanji.radical}}
            </div>
            <div class="column is-2">
                <p>Trazos</p> {{kanji.strokes}}
            </div>
            <div class="column is-2">
                <p>Nivel</p> <router-link class="has-text-grey-dark" v-bind:to="'/levels/' + kanji.lvl">{{kanji.lvl}}</router-link>
            </div>
        </div>

        <div class="columns is-centered is-multiline m-t-md m-b-sm">
            <div class="column is-12">
                <p class="is-size-5">Palabras</p>
            </div>

            <div v-for="word in kanji.words" :key="word.kotoba" class="column is-4">
                <Word v-bind:word="word"/>
            </div>

        </div>

    </section>
</template>

<script>

import Word from '@/components/Word.vue'

export default {
    name: 'kanji',

    props: {
        kanji: Object
    },

    components: {
        Word
    },

    data: function() {
        return {
            test: 'Kanji Test!'
        }
    }
}
</script>

<style lang="sass">

</style>
