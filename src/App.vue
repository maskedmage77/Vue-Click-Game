<template>
    <h1>Reaction Timer Game</h1>
    <button @click="start" :disabled="isPlaying">Play</button>
    <Block v-if="isPlaying" :delay="delay" @end="endGame"/>
    <Results v-if="showResults" :score="score"/>
</template>

<script>
    import Block from './components/Block.vue'
    import Results from './components/Results.vue'

    export default {
        name: 'App',
        components: { Block, Results },
        data() {
            return {
                isPlaying: false,
                delay: null,
                score: null,
                showResults: false
            }
           
        },
        methods: {
            start() {
                this. delay = 2000 + Math.random() * 5000
                this.isPlaying = true
                this.showResults = false
            },
            endGame(reactionTime) {
                this.score = reactionTime
                this.isPlaying = false
                this.showResults = true
            }
        }
    }
</script>

<style>
    body{
        background-color: black;
    }
    #app {
        font-family: Avenir, Helvetica, Arial, sans-serif;
        -webkit-font-smoothing: antialiased;
        -moz-osx-font-smoothing: grayscale;
        text-align: center;
        color: white;
    }
</style>
