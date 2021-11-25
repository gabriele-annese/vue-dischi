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

export default {
  name: 'App',
  components: {
    Header,
  }
}
</script>

<style lang="scss">
main{
  background-color: #1d2d3c;
}
</style>
