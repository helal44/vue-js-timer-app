<script setup>
import HelloWorld from './components/HelloWorld.vue'
import TheWelcome from './components/TheWelcome.vue'

import block from './block.vue'
import result from './result.vue'
</script>

<template>


  <h1>Timer Game</h1>
  <br>
  <button @click="start" :disabled="isplaying">play</button>
  <br>
    <block v-if="isplaying" :delay="delay" @end="endgame"/>
    <br>
    <result v-if="show" :score="score"/>
</template>

<script>
  export default {
    name:'app',
    components:{block ,result},


    data(){
      return{
        isplaying:false,
        delay:null,
        score:null,
        show:false
      }
    },


    methods: {
      start(){
        this.delay=2000 + Math.random() * 5000
        this.isplaying=true
        this.show=false
        console.log(this.delay)
      },
      endgame(time){
        this.score=time
        this.isplaying=false
        this.show=true
      }
    },
  }
</script>


<style scoped>

button{
  background: green;
  color: white;
  border: none;
  padding: 10px 20px;
  border-radius: 4 px;
  font-size: 16 px;
  cursor: pointer;
}

button[disabled]{
  opacity: .2;
  cursor: not-allowed;
}

</style>
