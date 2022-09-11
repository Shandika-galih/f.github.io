<template>
  <div class="card mx-4" id="top">
  <div class="card-header pb-0">
      <h2>TAMBAH USER</h2>
  </div>
  <div class="card-body px-3 pt-0 pb-2">
      <div class="mb-3">
      <label for="Email" class="form-label fs-5 text-uppercase font-weight-bolder opacity-7">Email</label>
      <input type="email" class="form-control" id="Email" v-model="email">
      </div>
      <div class="mb-3">
      <label for="Nama" class="form-label fs-5 text-uppercase font-weight-bolder opacity-7">Nama</label>
      <input type="text" class="form-control" id="Nama" v-model="name">
      </div>
      <button @click="post()" class="btn btn-primary">Simpan</button>
      <div id="email"></div>
      <div id="name"></div>
  </div>
  </div>
</template>

<script>
  import axios from 'axios';
  export default{
      name: "projects-table",
  data() {
      return{
      email: '',
      name: '',
      errors: []
      }
  },
  methods: {
      post() {
      axios.post('https://reqres.in/api/users', {
          email: this.email,
          name: this.name
      })
      .then(response => {})
      .catch(e => {
          this.errors.push(e)
      })
      document.getElementById('email').innerHTML = '<div class="fs-4">Email : ' + this.email + '</div>'
      document.getElementById('name').innerHTML = '<div class="fs-4">Nama : ' + this.name + '</div>'
  }
  }
}
</script>