<template>
   <p class="time">reaction time: {{ score }} ms</p>
   <p class=" rank">{{ rank }}</p>
</template>

<script>
export default {

    props:['score'],
    data(){
        return{
            rank:null
        }
    },
    mounted(){
        if(this.score <300){
            this.rank=' So Fast Ninja'

        }
        else if(this.rank <500){
            this.rank = 'not bad boy '
        }
        else{
            this.rank='try again'
        }
    }

}
</script>
<style>
  .rank{
    font-size: 2 em;
    color: rgb(24, 175, 175);
    font-weight: bold;
  }

  .time{
    font-size: 1 em;
    color: rgb(219, 18, 172);
    font-weight: bold;
  }
</style>