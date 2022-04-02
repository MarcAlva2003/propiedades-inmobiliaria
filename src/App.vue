<template>
    <AppHeader/>
  <router-view/>
    <AppFooter/>
</template>

<script>
import AppHeader from './components/AppHeader.vue'
import AppFooter from './components/AppFooter.vue'

export default {
  components:{
    AppHeader,
    AppFooter
  }
}
</script>

<style>
body{
  margin: 0;
  padding: 0;
  font-size: 16px; /*1rem = 10px*/
  background-color: rgb(216, 215, 215);
  font-family: 'PT Sans', sans-serif;
}
*, *:before, *:after{
    box-sizing: inherit;
}
p,a,h1,h2,h3,h4,h5{
  padding: 0;
  margin: 0;
}
</style>
