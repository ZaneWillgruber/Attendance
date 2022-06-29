<script setup lang="ts">

function getRandomInt(max) {
    return Math.floor(Math.random() * max);
}


const message = ref('code')

setInterval(() => {
    generateCode();
}, 5000)

const generateCode = () => {
    var result = '';
    const characters = 'ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789';

    for (var i = 0; i < 5; i++) {
        result += characters.charAt(getRandomInt(characters.length))
    }
    message.value = result;
}


</script>

<template>
    <div id="app">
        <p>{{ message }}</p>
        <button @click="generateCode()">Random Code</button>
    </div>
</template>