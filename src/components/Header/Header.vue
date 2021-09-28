<script setup>
    import './header.sass'
    defineProps({
        data: Object
    })
</script>


<template>
    <div class="match-container">
        <div class="match-result">
            <div class="host">
                <div class='team'>{{ data.host }}</div>
                <div class="flag">
                    <img src="https://cloudinary.fifa.com/api/v1/picture/flags-sq-5/UZB?tx=c_fill,g_auto,q_auto,w_256" alt="{{ data.host }} flag">
                </div>
                <div class="score">4</div>
            </div>
            <div class="visitor">
                <div class='team'>{{ data.visitor }}</div>
                <div class="flag">
                    <img src="https://cloudinary.fifa.com/api/v1/picture/flags-sq-5/GUA?tx=c_fill,g_auto,q_auto,w_256" alt="{{ data.visitor }} flag">
                </div>
                <div class="score">4</div>
            </div>
        </div>
        <div class='match-info'>
            <div class="tournament">FIFA Futsal</div>
            <div class="date">2021-09-12</div>
            <div class="time">17:00</div>
            <div class="venue">Vilnius Arena</div>
        </div>
    </div>
</template>


<style scoped>
    a {
    color: #42b983;
    }
</style>
