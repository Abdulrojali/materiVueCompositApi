<script>
// ref digunakan untuk menampung data baru pada kasus penggunaan setup komposit api
import {ref} from 'vue'
export default {
  // cara menggunakan setup composit api
  setup() {
    // cara inisiasi variabel di setup composit api
    // note apabila data di ubah tidak dapat di ubah secara langsung karena data bukan reactive
    const nama = ref('budi')
    const alamat = 'bandung'
    const datas=ref(null)
    const ubahdata=function(){
      datas.value.textContent='data di ubah'
    }
    // mendaftarkan variabel kedalam bentuk 
    return { nama, alamat,datas,ubahdata }
  }
}
</script>
<template>
  <h1 ref="datas">welcome {{ nama }} dengan alamat : {{ alamat }}</h1>
  <button @click="ubahdata">ubah</button>
  <!--dengan menggunakan ref kita dapat mengubah data secara cepat-->
  <input type="text" v-model="nama">
</template>
