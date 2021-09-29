<script setup>

    defineProps({
        list: Object,
        extras: Object,
    })

</script>

<script>

    export default {
        methods:{
            filterCaptain(playerNumber) {
                // devuelve true si el jugador es el capitan
                return playerNumber == this.extras.captain ? true : false
            },
            filterYellowCards(playerNumber) {
                // devuelve true si el jugador recibio tarjeta amarilla
                const isYellow = this.extras.yellowcards.filter( p => p === playerNumber ).length
                return isYellow == 0 ? false : true
            },
            filterGoals(playerNumber) {
                // devuelve el numero de goles, o false, si no ha marcado
                const isGoal = this.extras.goals.filter( p => p === playerNumber ).length
                return isGoal == 0 ? false : isGoal
            }
        }
    }

</script>

<template>

    <div class="player" v-for="player in list" :key="list[2]">
        <div class="dorsal">
            <strong>{{ player[2] }}</strong>
        </div>
        <div class="name">
            {{ player[0] }}
            <strong>{{ player[1].toUpperCase() }}</strong>
        </div>
        <div class="extras">
            <span v-if="filterYellowCards(player[2])"> TA </span>
            <span v-if="filterGoals(player[2])"> G.{{filterGoals(player[2])}} </span>
            <span v-if="filterCaptain(player[2])"> C </span>
        </div>
    </div>

</template>>