<script setup>
    import './result.sass'
    import TeamHeader from './TeamHeader.vue'
    defineProps({
        data: Object
    })
</script>


<template>
    <div class="match-header-container">
        <div class="match-result">

            <div class="host">
                <TeamHeader :team="data.host" />
            </div>
            <div class="divider">
                -
            </div>
            <div class="visitor">
                <TeamHeader :team="data.visitor" />
            </div>

        </div>

        <div class='match-info'>
            <div class="tournament">FIFA Futsal</div>
            <span> · </span>
            <div class="date">2021-09-12</div>
            <span> · </span>
            <div class="time">17:00</div>
            <span> · </span>
            <div class="venue">Vilnius Arena</div>
        </div>

    </div>
</template>

