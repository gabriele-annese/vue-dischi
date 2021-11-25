<template>
  <div id="app">
    <Header />
    <main>
      <Grid />
    </main>
  </div>
</template>

<script>
import Header from '@/components/Header.vue'
import Grid from '@/components/Grid.vue'
export default {
  name: 'App',
  components: {
    Header,
    Grid,
  }
}
</script>

<style lang="scss">
main{
  background-color: #1d2d3c;
}
</style>
