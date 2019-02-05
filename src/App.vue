<template>
  <div id="app">
    <!-- <img src="./assets/logo.png"> -->
    <div class="container row text-center a" >

    <router-link to="/"><h3>Home</h3></router-link>
    <router-link to="/about"><h3 class="space">about</h3></router-link>
  </div>
    <router-view/>
  </div>
</template>

<script>
import About from './components/About.vue';

export default {
  name: 'App',
   components : {
    'app-about' : About
  }
}
</script>
<style>
#app{

}
.a{
  margin-left:550px;
}
.space{
  margin-left:20px
}
</style>

