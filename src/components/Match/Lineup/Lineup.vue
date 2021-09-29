<script setup>
    import './lineup.sass'
    import Team from './Team.vue'
</script>

<script>
    export default {
        data() {
            return {
                host: {
                    team: 'Uzbekistan',
                    abrev: 'UZB',
                    flag: "https://cloudinary.fifa.com/api/v1/picture/flags-sq-5/UZB?tx=c_fill,g_auto,q_auto,w_256",
                    players: {
                        goalkeeper: [
                            ['Rustam', 'Umarov', 1]
                        ],
                        start: [
                            ['Ikhtiyor', 'Ropiev', 4],
                            ['Ilhomjon', 'Hamroev', 6],
                            ['Khusniddin', 'Nishonov', 8],
                            ['Davron', 'Choriev', 10]
                        ],
                        substitutions: [
                            ['Anaskhon', 'Rakhmatov', 2],
                            ['Mashrab', 'Adilov', 3],
                            ['Muzaffar', 'Akhadjonov', 5],
                            ['Dilshod', 'Rakhmatov', 7],
                            ['Akbar', 'Usmonov', 11]
                        ] 
                    },
                    captain: 1,
                    yellowcards: [11,6],
                    goals: [4,4,3,4]
                },
                visitor: {
                    team: 'Guatemala',
                    abrev: 'GUA',
                    flag: "https://cloudinary.fifa.com/api/v1/picture/flags-sq-5/GUA?tx=c_fill,g_auto,q_auto,w_256",
                    players: {
                        goalkeeper: [
                            ['William', 'Ramirez', 2]
                        ],
                        start: [
                            ['Edgar', 'Santizo', 5],
                            ['Jose', 'Masilla', 7],
                            ['Walter', 'Enriquez', 9],
                            ['Marvin', 'Sandoval', 10]

                        ],
                        substitutions: [
                            ['Pablo', 'Moran', 3],
                            ['Jose', 'Gonzalez', 4],
                            ['Alexander', 'Alay', 6],
                            ['Roman', 'Alvarado', 8],
                            ['Alan', 'Aguilar', 11]
                        ]
                    },
                    captain: 11,
                    yellowcards: [9],
                    goals: [10,10,11,11]
                }
            }
        }
    }
</script>

<template>
    <div class="lineup">

        <div class="host">
            <Team :data="host" :rival="visitor" />
        </div>
        <div class="visitor">
            <Team :data="visitor" :rival="host" />
        </div>

    </div>
</template>
