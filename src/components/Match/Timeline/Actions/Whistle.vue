<script setup>
    defineProps({
        data: Object
    })
</script>

<template>
        <div class="time-icon">
            <div class="icon">
                <svg xmlns="http://www.w3.org/2000/svg" class="ionicon" viewBox="0 0 512 512"><title>Time</title><path d="M256 64C150 64 64 150 64 256s86 192 192 192 192-86 192-192S362 64 256 64z" fill="none" stroke="currentColor" stroke-miterlimit="10" stroke-width="32"/><path fill="none" stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="32" d="M256 128v144h96"/></svg>
                </div>
            <div class="min">{{data.min}} '</div>
        </div>
        <div class="message">
            <div class="text">{{data.txt}}</div>
        </div>
</template>

<style lang="sass">
.whistle
    background-color: #e4e8f0
    .message
        .text
            font-size: 3rem
            padding-top:1rem
</style>
    