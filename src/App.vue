<template>
  <AppHeader/>
 <h1>{{title}}</h1>
 <p class="bg-red-500">I want to know you</p>
 <h1 class="text-3xl font-bold underline">
    Hello world!
  </h1>
</template>

<script>
import AppHeader from './components/AppHeader.vue';

  export default{
    components:{ AppHeader},
    data(){
      return { 
        title: "hey v3 checked",
      }
    }
  }
</script>


