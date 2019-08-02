<template>
  <div id="app">
    <img v-show="showLogo" @click="showLogo=!showLogo"  alt="Vue logo" src="./assets/logo.png">
    
    <counter-button :count="0"/>
    <counter-button :count="0"/>
    <counter-button :count="0"/>
    <counter-button :count="0"/>
    
  </div>
</template>

<script>
import CounterButton from './components/CounterButton.vue'
import { setTimeout } from 'timers';

export default {
  name: 'app',
  components: {
    CounterButton
  },
  data:function() {
    return{
      showLogo: true             
    }
  },
  watch:{
    showLogo:function(newVal){
      if(!newVal){
        setTimeout(() => this.showLogo=true,1000)
      }
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
