<template>
  <div class="container">
      <div v-if="musicList !== null" class="row p-3 justify-content-center">
          <div  v-for="(elMusic, index) in musicList" :key="`elMusic-${index}`"
          class="col-6 col-md-4 col-lg-3 mb-5 p-2 m-2 card-music text-center ">
           <img :src="elMusic.poster" :alt="elMusic.title">
              <Card 
                :title="elMusic.title"
                :subTitle="elMusic.author"
                :year="elMusic.year"
                :Text="elMusic.genre"
              />
          </div>
      </div>
     <Loader v-else />
  </div>
</template>

<script>
import axios from 'axios';
import Card from '@/components/Card.vue'
import Loader from '@/components/Loader.vue'
export default {
   name: 'Grid',
   components:{
       Card,
       Loader,
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
           }, 4000);
       }
   }
}
</script>

<style lang="scss" scoped>
.card-music{
    position: relative;
    display: flex;
    flex-direction: column;
    min-width: 0;
    word-wrap: break-word;
    background-color: #2e3a46;
    color: #fff;
    background-clip: border-box;
    border: 1px solid rgba(0, 0, 0, 0.125);
    border-radius: 0.25rem;
}
</style>