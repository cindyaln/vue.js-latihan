<template>
  <div>
    <h2>Formulir</h2>
    <form @submit.prevent="submitForm">
      <label for="">Nama</label>
      <input type="text" v-model="kontak.nama" :class="{ 'is-invalid': isInvalidName }" required>
      <div v-if="isInvalidName" class="error-message">Nama harus isi disini</div>
      <br>
      <label for="">Email</label>
      <input type="email" v-model="kontak.email" :class="{ 'is-invalid': isInvalidEmail }" required>
      <div v-if="isInvalidEmail" class="error-message">Email harus isi disini</div>
      <br>
      <button type="submit">Simpan</button>
    </form>
    <div v-if="showResult">
      nama : {{ name }} <br>
      email : {{ email }}
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
        email: '',
      },
      showResult: ref(false),
      name: ref(''),
      email: ref(''),
    };
  },
  methods: {
    submitForm() {
      this.name = this.kontak.nama;
      this.email = this.kontak.email;
      this.showResult = true;
    },
  },
  computed: {
    isInvalidName() {
      return this.name.length < 1;
    },
    isInvalidEmail() {
      return this.email.length < 1;
    },
  },
};
</script>

<style>
h2 {
  color: rgb(0, 0, 0);
}
.error-message {
  color: red;
  margin-top: 5px;
}
.is-invalid {
  border-color: red;
}
</style>