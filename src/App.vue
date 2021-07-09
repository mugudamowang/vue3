<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <h2>Welcome to MUGU</h2>
  <button v-for="(item, index) in datalist" :key="index" @click="select(index)">
    {{index}}:{{item}}
  </button>
  <p>you have choose {{selectItem}}</p>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue'


export default defineComponent({
  name: 'App',
  //setup集合了以前vue2的data,methods等, 直接书写
  setup(){
    const datalist = ref(["oliver","stack","bukun"]);
    const selectItem = ref("");
    const select = (index:number)=>{
      selectItem.value = datalist.value[index];
    };
    return{
      //写完要在此处return
      datalist,selectItem,select
    }
  }
})
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
