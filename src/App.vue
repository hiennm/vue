<template>
  <div id="app">
    <img v-show="showLogo" @click="showLogo=!showLogo"  alt="Vue logo" src="./assets/logo.png">
    
    <HelloWorld v-for="x in 10" :msg="title + x" :key="x"/>
    
    <ul>
      <li v-for="(value, name, index) in list" :key="value">
        {{index+1}}. {{name.charAt(0).toUpperCase()+name.substring(1)}} : {{value}}
      </li>
    </ul>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import { setTimeout } from 'timers';

export default {
  name: 'app',
  components: {
    HelloWorld
  },
  data:function() {
    return{
      showLogo:true,
      title: 'Hi there',
      list: {
        name:'Hien',
        age: 38
      }          
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
