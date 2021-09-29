
<script setup>
  import Match from './components/Match/Match.vue'
  import Result from './components/Result/Result.vue'
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
  <Result :data="data" />
  <Match />
</template>

<style>
@import url('https://fonts.googleapis.com/css2?family=Open+Sans+Condensed:ital,wght@0,300;0,700;1,300&display=swap');

:root{
  --header-bg-color: #000f2c;
  --match-bg-color: #f7f9fc;
  --lineup-title-bg-color: #e4e8f0;
  --active-link-color: #1277d9;
  --breakpoint-tablet: 768px;
}
body {
  margin: 0;
  padding: 0;
  font-family: 'Open Sans Condensed';
  background-color: var(--match-bg-color)
}

</style>