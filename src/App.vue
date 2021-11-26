<template>
  <div id="app">
    <Header  @changeGen="selectGen"/>
    <main>
      <Grid :musicArray="filterGen"/>
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
           textGen: '',
       };
   },
  computed:{
    filterGen(){
      if(this.textGen === ""){
        return this.musicList
      }

       return this.musicList.filter(item =>{
              return item.genre.includes( this.textGen )
       });
      }
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
       },
       selectGen(text){
         this.textGen = text;
       },
   }
}
</script>

<style lang="scss">
html{
  width: 100%;
  height: 100%;
  background-color: #1d2d3c;
}
main{
  background-color: #1d2d3c;
}
</style>
