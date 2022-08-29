<template>
  <div class="topbar">
      <p>Spotify</p>
      <div class="selectionGenre">
    <select name="myGenre" id="myGenre">
      <option value="we">{{Genre}}</option>
    </select>
  </div>
  </div>
</template>

<script>
export default {
    name: 'myTopbar',
    props: {
      Genre: String
    }
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