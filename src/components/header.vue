<template>
  <header>
    <div class="container">
      <div class="row">
        <div class="col-12 d-flex justify-content-start align-items-center ms_header-col ">
          <img src="https://upload.wikimedia.org/wikipedia/commons/7/75/Spotify_icon.png" alt="Spotify_icon.png">
        </div>
      </div>
    </div>
  </header>
</template>

<script>
export default {
    name: 'Header'
}
</script>

<style lang="scss" scoped>
@import '../assets/style/globals.scss';

  header{
    background-color: $spotifymenucolor;
  }
  .ms_header-col{
    height: 80px;
    img{
      height: 50px;
  }
  }
  
</style>