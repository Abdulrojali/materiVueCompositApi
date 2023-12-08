<script>
import {ref,computed} from 'vue'
export default{
  setup(){
    const listMhs=ref(
      [
        {id:1,nama:'budi',alamat:'bandung',usia:20,semester:3,jurusan:'sistem informasi'},
        {id:2,nama:'ahmad',alamat:'sukabumi',usia:19,semester:1,jurusan:'teknik informatika'},
        {id:3,nama:'nabila',alamat:'jakarta',usia:21,semester:6,jurusan:'akutansi'},
        {id:4,nama:'zara',alamat:'bekasi',usia:19,semester:1,jurusan:'manajemen'}
      ]
    )
    const search=ref('')
    const maaping=computed(()=>{
      listMhs=listMhs.value.filter((user)=>user.nama.includes(search.value))
    })
    return{listMhs,search,maaping}
  }
}
</script>

<template>
  <div class="container">
    <div class="content">
      <h3>searching data</h3>
      <div class="search">
        <input type="text" v-model="search">
      </div>
      <div class="dataloop">
        <ul>
          <li v-for="data in listMhs" :key="data.id" >
          {{ data.nama }}
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>