
<script setup>
    import Players from './Players/Players.vue'

  defineProps({
    data: Object,
    rival: Object
  })
</script>

<script>

    export default {
        methods:{
            selectExtras(team){
                return { 
                    captain: team.captain,
                    yellowcards: team.yellowcards,
                    goals: team.goals
                }
            }
        }
    }

</script>

<template>

    <div class="team">

        <div class="active">
            <span class="name">
                {{data.team.toUpperCase()}}
            </span>
            <span class="flag">
                <img :src="data.flag" alt="flag">
            </span>
        </div>
        <div class="inactive">
            <span class="name">
                {{rival.abrev.toUpperCase()}}
            </span>
            <span class="flag">
                <img :src="rival.flag" alt="flag">
            </span>
        </div>
    </div>
    <div class="players">
        <div class="goalkeeper">
            <Players :list="data.players.goalkeeper" :extras="selectExtras(data)" />
        </div>
        <div class="start">
            <Players :list="data.players.start" :extras="selectExtras(data)" />
        </div>
        <div class="substitutions">
            <div class="title">SUBSTITUTIONS</div>
            <Players :list="data.players.substitutions" :extras="selectExtras(data)" />
        </div>
    </div>

</template>