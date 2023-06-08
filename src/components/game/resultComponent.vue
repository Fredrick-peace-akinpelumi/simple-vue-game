<template>
<div class="text-center mt-3">
  <b :class= " result=='You failed' ?'text-danger fs-2' :'text-success fs-2'">{{result}}</b>
</div>
</template>

<script>
export default {
    props:["score"],
    data(){
        return{
            result:null
        }
    },
    mounted(){
        if(this.score > 5000){
            this.result= "You failed"
        }else{
            this.result= "You succeeded"
        }
    }

}
</script>

<style>

</style>