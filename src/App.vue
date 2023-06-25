<script setup>
import { ref } from 'vue';
import cardComponent from './components/cardComponent.vue';
const users = ref([
  {
    name:"juan jose mejor amigo",
    email:"kakoso@gmail.com"
  },
  {
    name:"el gallo",
    email:"gallazo@gmail.com"
  }
])
let name, email;
const añadir= function(){
  const newUser={
    name:name,
    email:email
  }
  users.value.unshift(newUser)
}
const borrarTarjeta=function(index){
  users.value.splice(index,1)
}
const duplicarTarjeta=function(name,email){
  const newUser={
    name:name,
    email:email
  }
  users.value.unshift(newUser)
}
</script>

<template>
  <cardComponent v-for="(user,index) in users" :key="index" :name="user.name" :email="user.email" :index="index" @borrarTarjeta="borrarTarjeta" @duplicarTarjeta="duplicarTarjeta" />
  <div>
    <label class="text-white "> ingrese su nombre</label>
    <br>
    <input v-model="name" type="text">
    <br>
    <label class="text-white"> ingrese su correo</label>
    <br>
    <input v-model="email" type="text">
    <br>
    <button class="p-1 mt-3 bg-white rounded-lg" @click="añadir">enviar</button>
  </div>
</template>