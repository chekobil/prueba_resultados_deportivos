<script setup>
  import Menu from './Menu/Menu.vue'
  import Lineup from './Lineup/Lineup.vue'
  import Timeline from './Timeline/Timeline.vue'

  import './match.sass'

  defineProps({
    data: Object
  })

</script>

<template>
  <div class="match-container">
    <Menu />
    <div class="match">
      <Lineup />
      <Timeline />
    </div>
  </div>

</template>
