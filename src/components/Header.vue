<template>
  <header  
        class="p-2 d- d-flex justify-content-between align-items-center">
      <div class="logo">
         <img src="@/assets/logo (1).png" alt="">
      </div>
      <div>
        <select 
            class="form-select " aria-label="Default select example" v-model="generes"  @change="changeGen">
                <option value="">All genre</option>
                <option value="Rock">Rock</option>
                <option value="Pop">Pop</option>
                <option value="Jazz">Jazz</option>
                <option value="Metal">Metal</option>
        </select>
      </div>
  </header>
</template>

<script>
export default {
name : "Header",
data(){
    return {
        generes: ''
    };
},
methods:{
    changeGen(){
        console.log(this.generes)
    }
}
}
</script>

<style lang="scss" scoped>
header{
    background-color: #2e3a46;
    .logo{
        width: 100px;
        height: 100px;
        img{
            width: 100%;
            height: 100%;
            object-fit: contain;
        }
    }
}
</style>