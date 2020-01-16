<template>
  <div id="app" ref="content">
    <HelloWorld/>
    <HelloWorld block/>
    <input type="color" @change="setColor()" ref="controlColor">
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'app',
  components: {
    HelloWorld
  },
  methods: {
    setColor() {
      this.$refs.content.style.setProperty('--theme-color', this.$refs.controlColor.value );
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
