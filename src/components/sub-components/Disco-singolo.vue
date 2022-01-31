<template>
  <div class="col d-flex px-4">
    <div class="ms_disco-box">
      <img src="https://www.onstageweb.com/wp-content/uploads/2018/09/bon-jovi-new-jersey.jpg" alt="">
      <h3>Titolo</h3>
      <span> autore </span>
      <span> anno </span>
    </div>
  </div>
</template>

<script>
export default {
    name: 'Disco-singolo',
}
</script>

<style lang="scss" scoped>
@import '../../assets/style/globals.scss';

.ms_disco-box{
    min-height: 300px;
    width: 100%;
    padding: 15px;
    margin-top: 20px;
    background-color: $spotifymenucolor;
    text-align: center;
    display: flex;
    flex-direction: column;
    img{
      height: 70%;
      }
    h3{
        text-transform: uppercase;
        margin: 10px 0;
    }
    span{
      color: grey;

    }
}

</style>