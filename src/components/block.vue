<template>
  <div class="block" v-if="showblock" @click="stopTimer" >
    click me
  </div>
</template>

<script>
export default {

props:['delay'],

data() {
    return{
        showblock:false,
        timer:null,
        reactionTime:0
    }
},

    mounted(){
   setTimeout(() =>{
    this.showblock = true
    this. startTimer()
   },this.delay)
    },
methods:{
    startTimer() {
        this.timer = setInterval(() => {
            this.reactionTime+=10
            
            
        }, 10);

    },

    stopTimer() {
        clearInterval(this.timer)
        this.$emit('end', this.reactionTime)
        console.log(this.reactionTime);


        

    }
    },

}
</script>

<style>
.block{
    width:400px;
    padding:100px 0;
    background-color: #0faf87;
    color:white;
    margin: 40px auto;
    border-radius:20px;
    text-align: center;
}
</style>