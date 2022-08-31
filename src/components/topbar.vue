<template>
  <div class="topbar">
      <p>Spotify</p>
      <div class="selectionGenre">
    <select @change="$emit('changedGenre', filteredGenre)"  v-model="filteredGenre">
      <option v-for="(genre, index) in genreList"  :key="index" :value="genre">{{genre}}</option>
    </select>
  </div>
  </div>
</template>

<script>
export default {

  name: 'myTopbar',
  props: {
    genreList: Array
  },

  data() {
    return {
      filteredGenre: ''
    }
  },
} 


</script>

<style lang="scss">
  * {
    padding: 0;
    margin: 0;
    box-sizing: border-box;
  }

  
    .topbar {

        background-color: #303A45;
        display: flex;
        justify-content: space-evenly;
        align-items: center;
        width: 100%;
        height: 50px;
    }

</style>