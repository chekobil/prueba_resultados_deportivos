<script setup>
    defineProps({
        team: Object,
    })
</script>

<template>
    <div class='header-team'>
        <span class="name">{{ team.team }}</span>
        <span class="abrev">{{ team.abrev }}</span>
    </div>
    <div class="flag">
        <img :src="team.flag" alt="flag">
    </div>
    <div class="score">{{team.result}}</div>
</template> 