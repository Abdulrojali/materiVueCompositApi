<script>
import { computed, watch, watchEffect } from 'vue';
import {ref} from 'vue'
export default{
  setup(){
    const teks=ref('')
    const listMhs=ref(['budi','ahmad','rizky','zabar','nabila','putri','sinta'])
    const maapping=computed(()=>{
      return listMhs.value.filter((nama)=>nama.includes(teks.value))
    })

    // watch berjalan apabila component digunakan
    watch(teks,()=>{
      console.log('sedang ada perubahan',teks.value)
    })

    // watchEffect berjalan saat component di muat
    watchEffect(()=>{
      console.log('sedang berjalan',teks.value)
    })
    return{listMhs,teks,maapping}
  }
}
</script>

<template>
  <div class="content">
    <input type="text" v-model="teks">
    <ul>
      <li v-for="(data,index) in maapping" :key="index">{{ data }}</li>
    </ul>
  </div>
</template>