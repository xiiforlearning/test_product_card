<template>
  <div id="app">
    <Navbar />
    <router-view/>
  </div>
</template>

<script>
import M from 'materialize-css'
import Navbar from '@/components/Navbar.vue'
export default {
  mounted () {
    M.AutoInit()
  },
  components: {
    Navbar,
  }
}
</script>

<style lang="scss" scoped>
@import '~materialize-css/dist/css/materialize.min.css';
*{
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}
</style>
