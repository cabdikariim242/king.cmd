<template>
  <h1>Ninja Reaction Timer</h1>
  <button  id="btn" @click="start" :disabled="isplaying">play</button>
<block v-if="isplaying" :delay="delay" @end="endgame"/>
<result  v-if="showResult" :score="score"/>

</template>

<script>
import block from './components/block.vue'
import result from './components/result.vue'

export default {
  name: 'App',
  components: { block, result },

  data() {
    return{
      isplaying:false,
      delay: null,
      score:null,
      showResult:false
    }
  },
  methods: {
    start(){ 
      this.delay = 2000 + Math.random() *5000;
      this.isplaying = true,
      this.showResult = false
    },
    endgame(reactionTime) {
      this.score = reactionTime,
      this.isplaying = false,
      this.showResult = true
   
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #4444;
  margin-top: 60px;
}
#btn{
  background-color: rgb(48, 119, 48);
  border:none;
  padding:10px 20px;
  color:white;
  font-size: 20px;
  font-weight: 400;
  cursor: pointer;
}
#btn[disabled]{
  background-color: rgba(48, 119, 48, 0.432);
  cursor: not-allowed;
}
</style>
