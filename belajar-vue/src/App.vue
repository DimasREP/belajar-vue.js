<template>
  <div id="tugas">
    <h2>Formulir </h2>
    <form @submit.prevent="submitForm">
      <label for="nama">Nama : </label>
      <input class="{'is-invalid':is}" type="text" id="nama" v-model="kontak.nama" required/>
      <div v-if="isInvalidNama" class="error-message">Nama Harus Di Isi</div>
      <br>
      <label for="kelas">Kelas :</label>
      <input type="text" id="kelas" v-model="kontak.kelas" required />
      <div v-if="isInvalidKelas" class="error-message">Kelas Harus Di Isi</div>
      <br>
      <label for="alamat">Alamat :</label>
      <input type="text" id="alamat" v-model="kontak.alamat" required />
      <div v-if="isInvalidAlamat" class="error-message">Alamat Harus Di Isi</div>
      <br>
      <label for="nilai_mtk">Nilai Matematika</label>
      <input type="text" id="nilai_mtk" v-model="kontak.nilai_mtk" required />
      <div v-if="isInvalidNilai_mtk" class="error-message">Nilai Harus Di Isi</div>
      <br>
      <label for="nilai_indo">Nilai Indoesia</label>
      <input type="text" id="nilai_indo" v-model="kontak.nilai_indo" required />
      <div v-if="isInvalidNilai_indo" class="error-message">Nilai Harus Di Isi</div>
      <br>
      <label for="nilai_ipa">Nilai IPA</label>
      <input type="text" id="nilai_ipa" v-model="kontak.nilai_ipa" required />
      <div v-if="isInvalidNilai_ipa" class="error-message">Nilai Harus Di Isi</div>
      <br>
      <button type="submit">Kirim</button>
    </form>
    <div v-if="showResult">
      Nama : {{ nama }} <br>
      Kelas : {{ kelas }}<br>
      Alamat : {{ alamat }}<br>
      Nilai Matematika : {{ nilai_mtk }} <br>
      Nilai Bahasa Indonesia : {{ nilai_indo }} <br>
      Nilai IPA : {{ nilai_ipa }} <br>
      Total : {{ total }}<br>
      keterangan : {{ keterangan }}
    </div>
</div>  
</template>

<script>
import { ref } from 'vue';
export default {
  data() {
    return {
      kontak: {
        nama: '',
        kelas: ref(''),
        alamat: ref(''),
        nilai_mtk: ref(''),
        nilai_indo: ref(''),
        nilai_ipa: ref(''),
        total : 0,
        keterangan : ref('')
      },
      showResult: ref(false),
      nama: ref(''),
      kelas: ref(''),
      alamat: ref(''),
      nilai_mtk: ref(''),
      nilai_indo: ref(''),
      nilai_ipa: ref(''),
      total : 0,
      keterangan : ref('')
    };

  },
  computed: {
    isInvalidNama() {
      return this.kontak.nama.length < 3;
    },
    isInvalidKelas() {
      return this.kontak.kelas.length < 3;
    },
    isInvalidAlamat() {
      return this.kontak.alamat.length < 3;
    },
    isInvalidNilai_mtk() {
      return this.kontak.nilai_mtk.length < 1;
    },
    isInvalidNilai_indo() {
      return this.kontak.nilai_indo.length < 1;
    },
    isInvalidNilai_ipa() {
      return this.kontak.nilai_ipa.length < 1;
    }
  },
  methods: {
    submitForm() {
      this.nama = this.kontak.nama;
      this.kelas = this.kontak.kelas;
      this.alamat = this.kontak.alamat;
      this.nilai_mtk = this.kontak.nilai_mtk;
      this.nilai_indo = this.kontak.nilai_indo;
      this.nilai_ipa = this.kontak.nilai_ipa;
      this.total = parseInt(this.nilai_mtk) + parseInt(this.nilai_indo) + parseInt(this.nilai_ipa);
      if (this.total >= 240) {
        this.keterangan = "Lulus"
      }else {
        this.keterangan = "Tidak Lulus"
      }
      this.showResult = true;
      
    },
  },
};
</script>

<style>
h1 {
  color: blue;
}

.error-message {
  color: red
}
</style>
