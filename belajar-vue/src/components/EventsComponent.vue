<template>
    <div>
      <h1>Aplikasi Vue.js Gue</h1>
      <MyComponent
        :nama="nama"
        :umur="umur"
        @greeted="onGreeted"
      ></MyComponent>
      <slot nama="footer"></slot>
    </div>
  </template>
  
  <script>
import MyComponent from './Mycomponent.vue';
  
  export default {
    components: {
    MyComponent
},
    data() {
      return {
        nama: 'Amalia Rahma',
        umur: 25
      };
    },
    methods: {
      onGreeted() {
        console.log('Kamu udah disapa');
      }
    }
  }
  </script>