<script setup>
    import { ref, computed } from 'vue'

    let count = ref(0)
    let inpVal
    // function setValue(input){
    //     inpVal = ref(input)
    //     console.log(inpVal)
    // }

    // function getInput(){
    //     return inpVal
    // }

</script>

<template>
    <h1
    v-html="count"
    v-bind:class=" 'danger' "
    />
    <button @click="count++">Добавить</button>
    <button @click="count--">Удалить</button>

    <input
    v-model="input"
    @input="setValue(input)"
    >
    <h1 >{{input}}</h1>
    
</template>

<style scoped lang = "sass">
.danger
    color: red
.primary
    color: green
</style>