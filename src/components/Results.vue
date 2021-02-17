<template>
    <p>Reaction Time: {{ score }}ms</p>
    <p class="rank">{{ rank }}</p> 
</template>

<script>
    export default {
        props: ['score'],
        data() {
            return {
                rank: null
            }
        },
        mounted() {
            if (this.score < 100) {
                this.rank = 'SPEED DEMON!!!'
            }
            else if (this.score < 200) {
                this.rank = 'quickdraw!'
            }
            else if (this.score < 400) {
                this.rank = 'respectable.'
            }
            else {
                this.rank = 'try again you snail.'
            }
        }
    }
</script>

<style>
    .rank {
        color: crimson;
    }
</style>