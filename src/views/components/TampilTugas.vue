<template>
<div class="card mb-4">
    <div class="card-header pb-0">
        <h6>User table</h6>
    </div>
    <div class="card-body px-0 pt-0 pb-2">
        <div class="table-responsive p-0">
            <table class="table align-items-center justify-content-center mb-0">
                <thead>
                    <tr>
                        <th lass="text-uppercase text-secondary text-xxs font-weight-bolder opacity-7">Foto</th>
                        <th class="text-uppercase text-secondary text-xxs font-weight-bolder opacity-7 ps-2">First Name</th>
                        <th class="text-uppercase text-secondary text-xxs font-weight-bolder opacity-7 ps-2">Last Name</th>
                        <th class="text-uppercase text-secondary text-xxs font-weight-bolder opacity-7 ps-2">Email</th>
                    </tr>
                </thead>
                <tbody v-if="get && get.length">
                    <tr v-for="get of get">
                        <td>
                            <img :src=get.avatar class="avatar avatar-xxl" />
                        </td>
                        <td>
                            <h5 class="font-weight-bold mb-0">{{get.first_name}}</h5>
                        </td>
                        <td>
                            <h5 class="font-weight-bold mb-0">{{get.last_name}}</h5>
                        </td>
                        <td>
                            <h5 class="font-weight-bold mb-0">{{get.email}}</h5>
                        </td>
                        <div class="ms-auto text-end">
                            <router-link :to="{name: 'delete', params:{id}}" class="btn btn-link text-danger text-gradient px-3 mb-0" href="javascript:;">
                                <i class="far fa-trash-alt me-2" aria-hidden="true"></i>Delete
                            </router-link>
                            <router-link :to="{name: 'put', params:{id}}" class="btn btn-link text-dark px-3 mb-0" href="javascript:;">
                                <i class="fas fa-pencil-alt text-dark me-2" aria-hidden="true"></i>Edit
                            </router-link>
                        </div>
                    </tr>
                </tbody>
            </table>
        </div>
    </div>
</div>
</template>

<script>
import axios from 'axios';
export default {
    name: "tampil-tugas",
    data() {
    return {
    get: []
    }
},
created() {
    axios.get('https://reqres.in/api/users')
    .then(response => {
        this.get = response.data.data
    })
}
}
</script> 
