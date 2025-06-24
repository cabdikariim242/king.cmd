<template>
  <div class="result">
    <p >The Reaction Time is:{{ score }} ms</p>
    <p class="rank"> {{ rank }}</p>
  </div>
</template>

<script>
export default {
 props:['score'],
    data() {
    return{
        rank: null
    }
 },
    mounted() {
    if (this.score < 250){
        this.rank = 'Ninja Fingers'
    }else if (this.score < 400) {
        this.rank = 'Rapid Reflexes'
    } else {
        this.rank = 'snail pace.......'
    }
},
}
</script>

<style scoped>
p{
    color: rgb(31, 88, 138);
}
.rank{
    font-size:1.4rem;
    color:#0faf87;
    font-weight: bold;
}
</style>