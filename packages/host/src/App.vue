<template>
  <div class="mt-10 text-3xl mx-auto max-w-6xl">
    <Header></Header>
    <div class="mt-10 text-3xl font-bold">
      <h3 class="text-center">HOST</h3>
      <p>Count : {{ count }}</p>
    </div>
      <button  @click="addOne" class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">Add One</button>
      <div class="mt-10">
      <router-view></router-view>
    </div>
    </div>
    
</template>
<script>
// import Header from 'remote/Header'
import { defineAsyncComponent } from 'vue'
const Header=defineAsyncComponent(()=>import("remote/Header"))
  export default {
    components:{
      Header
    },
    computed:{
      count(){
        return this.$store.state.count
      }
    },
    methods:{
      addOne(){
        this.$store.commit('addOne')
      }
    }
  }
</script>
