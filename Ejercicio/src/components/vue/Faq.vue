<script setup>
import { ref } from 'vue'

const val = ref('');
const large = ref(0)

function draw() {
    const words = val.value.split('')
    large.value = words.length
    console.log(words)
    
}

</script>

<template>
    <h1 class="mx-auto mb-4 text-center">Ejercicio</h1>
    <div class="mx-auto mt-4 w-36">
        <div class="w-4 h-6 inline-block bg-gray-500 mx-1"
        :class="{'bg-red-500': large >=1 && large <=3}"
        ></div>
        <div class="w-4 h-8 inline-block bg-gray-500 mx-1"
        :class="{'bg-orange-500': large <=4 && large <=6}"
        ></div>
        <div class="w-4 h-10 inline-block bg-gray-500 mx-1"
        :class="{'bg-yellow-500' large <=6 && large <=7}"
        ></div>
        <div class="w-4 h-12 inline-block bg-gray-500 mx-1"
        :class="{'bg-green-500' large >=7}"
        ></div>
        <input v-model="val" class="border rounded" /> <button @click="draw" class="rounded bg-blue-500">Calcular</button>
    </div>
</template>