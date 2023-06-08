 <template>
<div class="col-lg-6 mx-auto text-center ">
  <h3>Vue Js Reaction Timer</h3>
  <button class="btn btn-success " @click="start()" :disabled="isPlaying">PLAY</button>
</div>
<divComponent v-if="isPlaying" :delay="delay" @end="endGame"/>
<resultComponent :score="score" v-if="show"/>
</template>

<script>
import resultComponent from './resultComponent.vue';
import divComponent from './divComponent.vue';
export default {
    components:{divComponent, resultComponent},
    data(){
        return{
            isPlaying:false,
            delay:null,
            score:null,
            show:false,
        }
    },
    methods:{
        start(){
            this.isPlaying = true;
            this.delay= 2000 + Math.random() * 5000;
            this.show = false;
        },
        endGame(reactionTime){
            this.score=reactionTime
            this.isPlaying = false;
            this.show = true;
        }
    }

}
</script>

<style>

</style>