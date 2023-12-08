<script>
import componentsList from './componentList.vue'
import {ref,computed} from 'vue'
export default{
  setup(){
    const listArtikel=ref(
      [
        {id:1,judul:'tanaman hias ',deskripsi:'Lorem ipsum dolor sit amet consectetur adipisicing elit. Eum cupiditate repellat recusandae nostrum aperiam officia aliquam libero? Culpa veritatis repudiandae obcaecati officiis voluptas assumenda recusandae!'},
        {id:2,judul:'matematika dikstrit ',deskripsi:'Lorem ipsum dolor sit amet consectetur adipisicing elit. Eum cupiditate repellat recusandae nostrum aperiam officia aliquam libero? Culpa veritatis repudiandae obcaecati officiis voluptas assumenda recusandae!'},
        {id:3,judul:'algoritma struktur data ',deskripsi:'Lorem ipsum dolor sit amet consectetur adipisicing elit. Eum cupiditate repellat recusandae nostrum aperiam officia aliquam libero? Culpa veritatis repudiandae obcaecati officiis voluptas assumenda recusandae!'},
        {id:4,judul:'pemrograman website',deskripsi:'Lorem ipsum dolor sit amet consectetur adipisicing elit. Eum cupiditate repellat recusandae nostrum aperiam officia aliquam libero? Culpa veritatis repudiandae obcaecati officiis voluptas assumenda recusandae!'},
      ]
    )
    return{listArtikel}
  },
  components:{
    componentsList
  }
}
</script>

<template>
  <div class="container">
    <div class="content">
      <div class="col"
      v-for="data in listArtikel" :key="data.id">
      <componentsList :dataArtikel="data" ></componentsList>
      </div>
    </div>
  </div>
</template>
<style>
*{
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}
.container{
  width: 100%;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 10px;
}
.content{
  width: 85%;
  height: 100%;
  display: grid;
  grid-template-columns: repeat(auto-fill,minmax(250px,1fr));
  justify-content: center;
  align-items: center;
  grid-gap: 10px;
 
}
.col{
  padding:20px;
  border: 1px solid gray;
  border-radius: 5px;
  cursor: pointer;
}
</style>