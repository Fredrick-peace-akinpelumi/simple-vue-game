<template>
  <div class="text-center">
    <h2>Pisco game</h2>
    <p>Make sure you click the box before 5Seconds</p>

  <button class="btn btn-secondary w-25" @click="play()" :disabled="isPlaying">Play</button>
  </div>
  <animateDiv v-if="isPlaying" @end="endGame"/>
  <resultComponent :score="score" v-if="show"/>
</template>

<script>
import resultComponent from './resultComponent.vue'
import animateDiv from './animateDiv.vue'

export default {
    components:{animateDiv, resultComponent},
    data(){
        return{
            isPlaying:false,
            score:null,
            show:false,
            reactionTime: 0
        }
    },
    methods:{
        play(){
            this.isPlaying=true;
            this.show =false;
        },
        endGame(reactionTime){
       
                this.score=reactionTime
                this.isPlaying=false;
                this.show=true;
            
        },
    }
}
</script>

<style>

</style>