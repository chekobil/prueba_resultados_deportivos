<script setup>
  import HelloWorld from './components/HelloWorld.vue'
  import Header from './components/Header/Header.vue'
  import Menu from './components/Menu/Menu.vue'
</script>

<script>
    const data = {
      host: 'Uzbekistan',
      visitor: 'Guatemala'
    }

    export default {
        data() {
            return { data }
        }
    }
</script>

<template>

  <Header v-bind:data=data />
  <Menu />
  <HelloWorld msg="Hello Vue 3 + Vite" />

</template>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
