<template>
  
  <div class="block" v-if="showblock" @click="stoptimer">
    click me
  </div>

</template>

<script>
export default {

    props:['delay'],

    data(){
        return {
            showblock : false,
            timer:null,
            reactiontime:0
        }
    },
    mounted(){
        console.log('component mounted')
        setTimeout(() => {
            this.showblock=true
            this.starttimer()
            console.log(this.delay)
        }, this.delay);
    },
    updated(){
          console.log('component updated')
    },

    methods:{
        starttimer(){

            this.timer=setInterval(()=>{
                this.reactiontime +=10
            },10)
        } ,
        stoptimer(){

            clearInterval(this.timer)
            this.$emit('end',this.reactiontime)
            console.log(this.reactiontime)
        }
    }

}
</script>

<style>
  .block{
   width: 200px;
    border-radius: 20px;
    background: blueviolet;
    color: white;
    text-align: center;
    padding: 100px 0;
    margin: 40px auto;
  }
</style>