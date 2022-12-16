<script setup>
import { ref, reactive } from 'vue'

    const arr = reactive([]);
    const myInput = ref('')
    const inputValue = myInput;
   
    function addText(){
      if (this.myInput == '') console.warn()
      else if (this.myInput.length > 5) {
        arr.push(this.myInput.toUpperCase())
        this.myInput = ''
      }
    }

    function setValue() {
      if (inputValue.value.length < 11)
        this.myInput = inputValue.value
      else
        this.myInput = ''
    }

</script>

<template>
  <h1 :style="{
    color: myInput.length <= 5 ? 'darkred' : 'darkblue',
    fontSize: myInput.length <= 8 ? '48px' : '32px'
  }">Список задач</h1>
  <input v-model="myInput" @keyup.enter="addText()" @input="setValue()">
  <button @click="addText()">Добавить</button>
  <p v-if="arr.length">
    <p v-for="(elem, index) in arr" :key="elem">({{index+1}}) {{elem}}
      <button @click="arr.splice(index, 1)">Удалить</button>
    </p>
    <p>Всего записей: {{arr.length}} | Удовоенное: {{arr.length *2}}</p>
  </p>
  <p v-else>На данный момент записей нет. Добавьте чтоб они появились здесь.</p>
  
  
</template>

<style scoped lang="sass">
@use "sass:math"
input
  font-family: Arial, sans-serif
  background-color: gray
  border: 3px solid #FFFFFF
  font-size: 18px
  outline: none
  padding: 10px
  color: #FFFFFF
p
  font-family: Arial, sans-serif
  font-size: 18px
  color: black

</style>