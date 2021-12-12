<template>
  <div id="app">
    <star :active="false"/>
  </div>
</template>

<script>
import Star from './components/Star.vue'

export default {
  name: 'App',
  components: {
    Star
  }
}
</script>

<style>
#app {

}
</style>
