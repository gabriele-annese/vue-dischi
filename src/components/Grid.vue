<template>
  <div class="container">
      <div v-if="musicList !== null" class="row p-3">
          <div  v-for="(elMusic, index) in musicList" :key="`elMusic-${index}`"
          class="col-6 col-md-4 col-lg-3 mb-5 p-2 m-2 card-music text-center ">
              <img :src="elMusic.poster" alt="">
              <div class="text-card mt-2">
                    <h3 class="text-uppercase title">{{elMusic.title}}</h3>
                    <h4 class="author">{{elMusic.author}}</h4>
                    <span class="year">{{elMusic.year}}</span>
                    <span class="genre">{{elMusic.genre}}</span>
              </div>
          </div>
      </div>
     <div v-else >Loading...</div>
  </div>
</template>

<script>
import axios from 'axios';
export default {
   name: 'Grid',
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
           axios
           .get('https://flynn.boolean.careers/exercises/api/array/music')
           .then(result =>{
               console.log(result.data)
               this.musicList = result.data.response
               console.log(this.musicList)
           })
           .catch (err => console.log(err))
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
    .text-card{
        display: flex;
        flex-direction: column;
        .title{
            font-size: 23px;
            font-weight: 600;
        }
        .genre{
            color: #fff;
            font-weight:600;
            font-size: 18px;
        }
        .author,
        .year{
            color: #848381;
            font-weight:600;
        }
    }
}
</style>