<script setup>
    import './timeline.sass'
    import Goal from './Actions/Goal.vue'
    import Whistle from './Actions/Whistle.vue'
    import Default from './Actions/Default.vue'
    import Yellowcard from './Actions/Yellowcard.vue'
</script>

<script>
    export default {
        data() {
            return {
                timeline: [
                    {
                        min: 'FT',
                        type: 'whistle',
                        title: 'FT: Uzbekistan 4 - 5 Guatemala',
                        txt: 'The final whistle sounds.'
                    },
                    {
                        min: 40,
                        type: 'whistle',
                        txt: 'The referee brings the second period to an end.'
                    },
                    {
                        min: 40,
                        type: 'default',
                        txt: 'Assisted by WANDERLEY.'
                    },
                    {
                        min: 40,
                        type: 'goal',
                        team: 'Guatemala',
                        title: 'Uzbekistan 4 - 5 Guatemala',
                        txt: 'A. AGUILAR (Guatemala) scores!!'
                    },
                    {
                        min: 39,
                        type: 'default',
                        txt: 'WANDERLEY (Guatemala) takes a corner kick.'
                    },
                    {
                        min: 32,
                        type: 'yellowcard',
                        txt: 'CAMPAIGNAC (Guatemala) is booked by the referee.'
                    },
                    {
                        min: 0,
                        type: 'whistle',
                        txt: 'The referee signals the start of the first period.'
                    }
                ]
            }
        }
    }
</script>

<template>
    <div class="timeline-container">
        <div class="timeline">
            <div class="action" :class="t.type" v-for="t in timeline">
                <Default :data="t" v-if="t.type == 'default'" />
                <Goal :data="t" v-if="t.type == 'goal'" />
                <Whistle :data="t" v-if="t.type == 'whistle'" />
                <Yellowcard :data="t" v-if="t.type == 'yellowcard'" />
            </div>
        </div>
    </div>
</template>
