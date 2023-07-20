<script setup>
import { ref } from 'vue'

//interpolasi teks 
const msg = "Hallo World"

//rawrhtml (menggunakan html yang ada dalam variabel)
const rawrhtml = "<h2> Haii Semuanyaa <h2>"

//v-bind  (menggunakan atribut html ke vue js menggunakan v-bind)
const link = "https://chat.openai.com"

//aritmatika
const number = prompt("")
</script>

<template>
  <div id="app">
    <span>{{ msg }}</span>
    <br>
    <span v-html="rawrhtml" style="color: blue;"></span>
    <br>
    <a v-bind:href = "link">CHAT GPT    </a>
    <br>
    <p> {{ parseInt(number) }}</p> 
    <p> {{ number ? 'TRUE : 1' : 'FALSE : 0' }}</p>
    <br>
    <button :disabled="isButtonDisabled">Button</button>
  </div>
</template>