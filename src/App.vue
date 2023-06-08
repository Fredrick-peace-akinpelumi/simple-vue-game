<template>
<p></p>
  <!-- <h1>{{Name}}</h1>
  <Home title="Vue js class" content="welcome to vue class"> 
    <template v-slot:special>
      <p>LARAGIGS</p>
    </template>
    <h3>Welcome to vue class</h3>
    <p>Enjoy the moment</p>
  </Home> -->
  <game></game>
  <!-- <reaction-timer></reaction-timer> -->
  
</template>

<script>
import game from './components/game/playComponent.vue'
// import reactionTimer from './components/Reaction timer/reactionTimer.vue';


export default {
  components:{game, },
    data(){
      return {
        Name:"Peace akinpelu"
      }
    },
    methods:{
      handleClick(){
        console.log("Hello Vue");
      }
    }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  /* text-align: center; */
  color: #2c3e50;
  margin-top: 60px;
}
</style>
