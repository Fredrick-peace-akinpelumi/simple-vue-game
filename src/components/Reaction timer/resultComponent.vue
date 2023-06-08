<template>
 <div class="text-center">
     <p>Reaction Time - {{score}}ms</p>
  <p class="text-success fw-bold">{{rank}}</p>
 </div>
</template>

<script>
export default {
    props:["score"],
    data(){
        return {
            rank:null
        }
    },
    methods:{
        },
        mounted(){
            if (this.score < 250) {
                this.rank = "Fastest finger"
            }else if(this.score < 500) {
                this.rank = "Quite rapid"
            }else if(this.score < 750) {
                this.rank = "Quite rapid"
            }else{
                this.rank = "Snail Race"
            }
        }
}
</script>

<style>

</style>