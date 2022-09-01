<template>
  <div id="app">
    <MyTopBar @changedGenre="startSearch" :genreList= "genreList" />
    <MyMain @genresReady="myGenre"  :genreFromHeader = "genreFromHeader"/>
  </div>
</template>

<script>
import MyTopBar from "./components/topbar.vue";
import MyMain from "./components/myMain.vue";



export default {
  name: 'App',
  components: {
    MyTopBar,
    MyMain
},

data() {
  return {
    genreList: [],
    genreFromHeader: ''
  }
},

methods: {

myGenre(allGenres){
  this.genreList = allGenres;
    },
    startSearch(genreRecived){
      this.genreFromHeader = genreRecived; 
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
