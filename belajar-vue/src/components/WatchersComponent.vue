<template>
    <div v-if="umur > 18">
      <p>Selamat Datang {{ nama }}</p>
    </div>
    <div v-else>
      <p>Maaf Kamu Belum Cukup Umur</p>
    </div>
    <button @click="greet">SAPA</button>
  </template>
  
<script>
export default {
  props: ['nama', 'umur'],
  data() {
    return {
      pesan: 'Halo, ' + this.nama + '!'
    };
  },
  methods: {
    greet() {
      console.log('Halo, bro!');
    }
  },
  computed: {
    pesanSelamat() {
      return 'Selamat datang, ' + this.nama + '!';
    }
  },
  watch: {
    umur(newUmur, oldUmur) {
      console.log('Umur berubah dari', oldUmur, 'menjadi', newUmur);
    }
  }
}
</script>