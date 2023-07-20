<script setup>
import { ref } from 'vue'

let msg = ("Hello world")
let rawHtml = ("<li>Cooffie</li>") 
const checkedNames = ref([])
let a = 10
let b = 5
let c = a + b
</script>

<template>
  <div id="app">
  <span>{{ msg }}</span> <br>
  <span v-html="rawHtml"></span> 

<select v-model="selected"> <br>
  <option disabled value="">Please select one</option>
  <option>Cooffie Latte</option>
  <option>Espreso</option>
  <option>Ristreto</option>
  <option>Flat White</option>
  <option>Frappe</option>
  <option>Clod Brew</option>
  <option>Affogato</option>
</select>

<div>enter toppings: </div><br>
<input type="checkbox" id="jack" value="Jack" v-model="checkedNames">
<label for="jack">cake</label>
<input type="checkbox" id="john" value="John" v-model="checkedNames">
<label for="john">Wall’s Chocolate Deluxe</label>
<input type="checkbox" id="mike" value="Mike" v-model="checkedNames">
<label for="mike">Wall’s Oreo Cookies & Cream</label>

  <div v-bind:id="dynamicId"></div>
  <button v-bind:disabled="isButtonDisabled">Pesan</button>
  <br>
  bil 1 = {{ a }} <br> 
  bil 2 = {{ b }} <br>
  Hasil = b1 + b2 = {{ c }}
  </div>
</template>