<script>
import {ref} from 'vue'
export default{
    props:['dataArtikel'],
    setup(props){
        const judul=ref(props.dataArtikel.judul)
        const deskripsi=ref(props.dataArtikel.deskripsi)
        const id=ref(props.dataArtikel.id)
        const view=function(){
            console.log(props.dataArtikel.id)
            console.log(props.dataArtikel.judul)
            console.log(props.dataArtikel.deskripsi)
        }
        return {judul,deskripsi,id,view}
    }
}
</script>

<template>
    <div class="list">
        <h3>{{judul}}</h3>
        <p>{{deskripsi}}</p>
        <button @click="view">view</button>
    </div>
</template>

<style scoped>
.list{
    display: flex;
    flex-direction: column;
    gap: 8px;
}
.list button{
    display: inline-block;
    padding: 6px 8px;
    width: 70px;
    height: 30px;
    cursor: pointer;
    border-radius: 5px;
    background-color: red;
    color: white;
    text-transform: capitalize;
    border: none;
}
.list button:hover{
    opacity: .6;
}
.list p{
    font-size: .7em;
    font-weight: 500;
    font-family: 'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana, sans-serif;
}
.list h3{
    font-size: 2em;
    font-weight: 900;
}
</style>
