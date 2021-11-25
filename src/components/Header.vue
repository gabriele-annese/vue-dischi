<template>
  <header class="p-2">
      <div class="logo">
         <img src="@/assets/logo (1).png" alt="">
      </div>
  </header>
</template>

<script>
export default {
name : "Header"
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