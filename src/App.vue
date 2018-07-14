<template lang="pug">
  #app
    HelloWorld
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'app',
  components: {
    HelloWorld
  }
}
</script>

<style lang="sass">
  @import './sass/main.sass'
</style>
