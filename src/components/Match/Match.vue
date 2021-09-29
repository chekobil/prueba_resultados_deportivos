<script setup>
  import Lineup from './Lineup/Lineup.vue'
  import Timeline from './Timeline/Timeline.vue'

  import './match.sass'

  defineProps({
    data: Object
  })
</script>

<script>
  export default {
    data() {
      return {
        showLineup: true
      }
    }
  }
</script>

<template>
  <div class="match-container">
    <div class="menu">
        <div class="item" :class="{active: showLineup}" @click="showLineup=true">Line Up</div>
        <div class="item" :class="{active: !showLineup}" @click="showLineup=false">Timeline</div>
        <div class="item">Info</div>
    </div>
    <div class="match">
      <Lineup v-if="showLineup" />
      <Timeline v-else="showLineup" />
    </div>
  </div>

</template>
