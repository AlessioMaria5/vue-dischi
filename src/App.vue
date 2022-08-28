<template>
  <div id="app">
    <Topbar />
    <MyMain />
  </div>
</template>

<script>
import Topbar from "./components/topbar.vue";
import MyMain from "./components/myMain.vue";



export default {
  name: 'App',
  components: {
    Topbar,
    MyMain
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
