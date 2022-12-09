<script setup>
import { ref, reactive } from 'vue'

  const data = reactive({symbol: ""})
  function addText(value){
    data.symbol = value
  }

</script>

<template>
  <input v-model="myInput" @keypress.enter="addText(myInput)">
  <p v-if="data.symbol">{{data.symbol}}</p>
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