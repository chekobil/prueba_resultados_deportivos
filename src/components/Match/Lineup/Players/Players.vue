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

    <div class="player" v-for="player in list" :key="player[2]">
        <div class="dorsal">
            <strong>{{ player[2] }}</strong>
        </div>
        <div class="name">
            {{ player[0] }}
            <strong>{{ player[1].toUpperCase() }}</strong>
        </div>
        <div class="extras">
            <span class="card" v-if="filterYellowCards(player[2])">
                <div>YC</div>
            </span>
            <span class="icon" v-if="filterGoals(player[2])"> 
                <svg xmlns="http://www.w3.org/2000/svg" class="ionicon" viewBox="0 0 512 512"><title>Football</title><circle cx="256" cy="256" r="192" fill="none" stroke="currentColor" stroke-linecap="round" stroke-miterlimit="10" stroke-width="32"/><path fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="32" d="M256 175.15l-76.09 63.83L200 320h112l20.09-81.02L256 175.15zM332.09 238.98l52.87-22.4 25.78-73.26M447 269.97l-62.04-53.39M179.91 238.98l-52.87-22.4-25.78-73.26M65 269.97l62.04-53.39M256 175.15v-57.57l64-42.64M192 74.93l64 42.65M312 320l28 48-28 71M410.74 368H342M200 320l-28 48 28.37 71.5M101.63 368H172"/></svg>
                <div>{{filterGoals(player[2])}}</div>
            </span>
            <span class="icon" v-if="filterCaptain(player[2])">
                <svg xmlns="http://www.w3.org/2000/svg" class="ionicon" viewBox="0 0 512 512"><title>Star</title><path d="M480 208H308L256 48l-52 160H32l140 96-54 160 138-100 138 100-54-160z" fill="none" stroke="currentColor" stroke-linejoin="round" stroke-width="32"/></svg>
            </span>
        </div>
    </div>

</template>
