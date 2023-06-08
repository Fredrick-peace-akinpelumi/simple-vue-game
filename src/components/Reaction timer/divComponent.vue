<template>
  <div v-if="showBlock" class="p-5 col-lg-4 mt-5 text-center fs-2 card bg-warning text-light" @click="stopTimer()">Click this</div>
</template>

<script>
export default {
    props:["delay"],
    data(){
        return {
            showBlock: false,
            timer:null,
            reactionTime: 0
        }
    },
    mounted(){
        setTimeout(() => {
            this.showBlock = true;
            this.startTimer()
        }, this.delay);
    },
    methods:{
        startTimer(){
            // this.showBlock =false
            this.timer= setInterval(() => {
                this.reactionTime +=10
            }, 10);
        },
        stopTimer(){
            clearInterval(this.timer);
            this.$emit("end", this.reactionTime)
        }
    }
}
</script>

<style>

</style>