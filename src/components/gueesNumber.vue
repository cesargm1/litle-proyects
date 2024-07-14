<template>
    <label>
        Introducce un numero del 0 al 10 para adivinarlo 
        <input placeholder="0" v-model="UserguessNumber" type="number" >
        <button @click="checkNumber()">comprobar {{ correctNumber}}</button>
        <p v-if="result">Que suerte! El numero correcto es {{ correctNumber }}acertaste! 😁</p>
        <p v-else>El numero es incorrecto sigue intentandolo 😭</p>
        <p v-show="UserguessNumber > 10" :class="{'error':UserguessNumber}">El numero es muy alto Introducce un numero que sea 10 o menor</p>
    </label>
</template>

<script setup>
import {ref} from 'vue'
const UserguessNumber = ref("");
const correctNumber = ref(Math.floor(Math.random() * 10) +1);
const result = ref(false)


const checkNumber = ()  => {
    result.value = correctNumber.value === parseInt(UserguessNumber.value) 
    UserguessNumber.value = "" 
}

 
</script>

<style scoped>
.error{
    color: rgb(225, 45, 45);
    font-size: 1.5em;
}
</style>  