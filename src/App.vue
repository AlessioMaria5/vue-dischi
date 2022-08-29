<template>
  <div id="app">
    <Topbar @getMusicGenre= "ciao" />
    <MyMain  />
  </div>
</template>

<script>
import Topbar from "./components/topbar.vue";
import MyMain from "./components/myMain.vue";



export default {
  name: 'App',
  props: {
    musicGenre: String
  },
  components: {
    Topbar,
    MyMain
},

data() {
  return {
    newGenres: 'placeGenre'
  }
},

methods: {

myGenre(genre){
    this.newGenres = genre 
}
}

}
</script>

<style lang="scss">
#app {

  * {
    padding: 0;
    margin: 0;
    box-sizing: border-box;
  }

  
}
</style>
