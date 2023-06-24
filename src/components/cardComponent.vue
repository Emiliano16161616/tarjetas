<script setup>
const props= defineProps({
    name:{
        type: String,
        default: "no hay nombre"
    },
    email:{
        type: String,
        default: "no hay correo"
    },
    index:{
        type:Number
    }
})
const borrarTarjeta=function(index){
    emit("borrarTarjeta",index)
}
const emit= defineEmits("borrarTarjeta")
</script>

<template>
  <div class="flex bg-red-500 h-72 w-72">
    <div>
        <img src="https://i.pinimg.com/originals/24/f1/f5/24f1f54f147a70157d56180b5192f6df.jpg" class="w-24 h-40" alt="">
        <p>
            {{ props.name }}
        </p>
        <p>
            {{props.email}}
        </p>
        
    </div>
    <div class="flex ">
        <div>
            <p class="bg-blue-600 p-[15px] rounded-lg" @click="borrarTarjeta(props.index)">
                x 
            </p>
        </div>
        <div>
            <p class="bg-purple-600 p-[15px] ml-5 rounded-lg" >
                add
            </p>
        </div>
    </div>
  </div>
</template>