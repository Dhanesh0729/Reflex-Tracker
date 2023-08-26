<template>
  <h1>Reaction Timer</h1>
  <div class="butt">
    <button @click="start">Test Your Speed</button>
    <button @click="stop">Reset</button>
    <br>
  </div>
  <block v-if="isplaying" :delay="delay" @endgame="endfunc"/>
  <Results v-if="showResult" :ScoreR="Score"/>
</template>

<script>
import block from "./components/block.vue"
import Results from "./components/results.vue"

export default {
  name: 'App',
  components: {block,Results},
  data(){
    return{
      isplaying: false,
      delay: null,
      Score: null,
      showResult: false
    }
  },
  methods:{
    start(){
      this.delay = 2000 + Math.random()*5000
      this.isplaying= true
      // this.showResult= false
    },
    stop(){
      this.isplaying= false
      this.showResult= false
    },
    endfunc(end){
      this.Score=end,
      this.isplaying=false,
      this.showResult = true
    }
  }
}
</script>

<style>

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #1e1e1e;
  margin-top: 60px;
}

.butt button{
  margin: 20px;
  padding: 10px 20px;
  font-size: 15px;
  border-radius: 5px;
  border: 1px solid #e6e6e6;
  background-color: whitesmoke;
  cursor: pointer;
  box-shadow: 0px 0px 10px 0px rgba(0,0,0,0.25);
  transition: 0.3s ease-in-out;
}
.butt button:hover{
  background-color: #e6e6e6;
  transform: scale(1.1) translateY(-3px);
}
</style>
