<script setup>
import { ref, reactive } from 'vue'

  let data = reactive([])

  function addText(value){
    data.push(value[0].toUpperCase() + value.slice(1));
    this.value = ""
  }

</script>

<template>
  <input v-model="myInput" @keypress.enter="addText(myInput)">
  <p v-if="data.length"
  v-for="(elem, index) in data"
  :key="elem">
    {{elem}}
    <button @click="data.splice(index, 1)">Удалить</button>  
  </p>
  <p v-else>Текста нет</p>
</template>

<style scoped lang="sass">

input
  font-family: Arial, sans-serif
  background-color: #eaaa00
  border: 3px solid #FFFFFF
  font-size: 18px
  outline: none
  padding: 10px
  color: #FFFFFF
p
  font-family: Arial, sans-serif
  font-size: 18px
  color: #FFFFFF


</style>