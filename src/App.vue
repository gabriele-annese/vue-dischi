<template>
  <div id="app">
    <Header />
    <main>
      <Grid :musicList="musicList"/>
    </main>
  </div>
</template>

<script>
import axios from 'axios';
import Header from '@/components/Header.vue'
import Grid from '@/components/Grid.vue'
export default {
  name: 'App',
  components: {
    Header,
    Grid,
  },
  data(){
       return{
           musicList: null,
       };
   },
   created(){
       this.getMusic();
   },
   methods:{
       getMusic(){
           setTimeout(() => {
               axios
               .get('https://flynn.boolean.careers/exercises/api/array/music')
               .then(result =>{
                   console.log(result.data)
                   this.musicList = result.data.response
                   console.log(this.musicList)
               })
               .catch (err => console.log(err))
           }, 2000);
       }
   }
}
</script>

<style lang="scss">
main{
  background-color: #1d2d3c;
}
</style>
