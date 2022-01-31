<template>
  <main>
    <div class="container p-5">
      <div class="row row-cols-5">
        <disco-singolo
         v-for="(element, index) in dischiArray"
         :key="index"
         :disco="element" />

      </div>
    </div>
  </main>
</template>

<script>
import discoSingolo from './sub-components/Disco-singolo.vue'
import axios from 'axios';
export default {
  name: 'Main',
  components: { 
    discoSingolo 
    },
  data(){
    return{
      apiUrl: "https://flynn.boolean.careers/exercises/api/array/music",
      dischiArray: []
    }
  },
  created(){
    this.getDischi();
    console.log(this.dischiArray);
  }, 
  
  methods: {
    getDischi(){
        axios
            .get(this.apiURL)
            .then( (risposta) => {
                // handle success
                this.dischiArray = risposta.data.response;
            })
            .catch(function (error) {
                // handle error
                console.log(error);
            });
        }
    }
}

</script>

<style lang="scss" scoped>
@import '../assets/style/globals.scss';
main{
  background-color: $spotifybackgroundcolor;
}
</style>