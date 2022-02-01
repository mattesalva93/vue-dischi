<template>
  <div class="col d-flex px-4">
    <div class="ms_disco-box">
      <img :src="disco.poster" :alt="disco.poster" class="img-fluid">
      <h3>{{disco.title}}</h3>
      <span> {{disco.author}} </span>
      <span> {{disco.year}} </span>
    </div>
  </div>
</template>

<script>
export default {
    name: 'Disco-singolo',
    props: {
      disco: Object
    }
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
    h3{
        text-transform: uppercase;
        margin: 10px 0;
    }
    span{
      color: grey;

    }
}

</style>