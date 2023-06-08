<template>
  <div @click="stop()" class="mt-4 w-25 p-3 text-white text-center bg-danger animate">
    <h2>Click me</h2>
  </div>
  <div @click="stop()" class="mt-4 w-25 h-50 p-3 text-white text-center bg-primary animate1">
    <h2>Click me</h2>
  </div>
  <div @click="stop()" class="mt-4 w-25 p-3 text-white text-center bg-info animate2">
    <h2>Click me</h2>
  </div>
  <div @click="stop()" class="mt-4 w-25 p-3 text-white text-center bg-primary animate3">
    <h2>Click me</h2>
  </div>
</template>

<script>
export default {
    data(){
        return{
            showBlock:false,
            reactionTime:0,
        }
    },
mounted(){
    this.startTimer()
},
methods:{
        startTimer(){
            
            this.timer= setInterval(() => {
                this.reactionTime +=10
            }, 10);
        },
        stop(){
            clearInterval(this.timer);
            this.$emit("end", this.reactionTime)
        }
}
}
</script>

<style>
    .animate{
        animation-duration: 0.7s;
        animation-name: box;
        animation-direction: alternate;
        animation-play-state: running;
        animation-iteration-count: infinite;
    }
    @keyframes box {
        from{
            margin-left: 100%;
        }
        to{
            margin-left: 0%;
        }
    }
    .animate1{
        animation-duration: 0.7s;
        animation-name: box1;
        animation-direction: alternate;
        animation-play-state: running;
        animation-iteration-count: infinite;
    }
    @keyframes box1 {
        from{
            /* margin-top: 100%; */
            transform: translateY(80vh);
        }
        to{
            /* margin-top: 0%; */
            transform: translateX(0%);

        }
    }
    .animate2{
        animation-duration: 0.7s;
        animation-name: box2;
        animation-direction: alternate;
        animation-play-state: running;
        animation-iteration-count: infinite;
    }
    @keyframes box2 {
        100%{
            /* margin-left: 100%; */
            transform: translateX(100vh);
        }
        75%{
            /* margin-left: 0%; */
            transform: translateY(50vh);
        }
        0%{
            transform: translate(0vh)
        }
    }
    .animate3{
        animation-duration: 0.7s;
        animation-name: box3;
        animation-direction: alternate;
        animation-play-state: running;
        animation-iteration-count: infinite;
    }
    @keyframes box3 {
        100%{
            /* margin-left: 100%; */
            transform: translateX(130vh);
        }
        75%{
            /* margin-left: 0%; */
            transform: translateY(-50vh);
        }
        0%{
            transform: translate(0vh)
        }
    }
</style>