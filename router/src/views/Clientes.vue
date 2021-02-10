<template>
    <div class="clientes">
        <h1>Cliente desde el view: </h1>
        
        <router-link to="{ name:'Clientes', params:{id: item} }" 
        v-for="(item,index) of perfiles" :key="index">
            <button>
                Foto {{ item }}
            </button>
        </router-link>





        <Perfil />

        <!-- moverse por ruta con JS -->
        <button @click="Inicio">Inicio</button>
        <button @click="Anterior">Anterior</button>
        <button @click="Siguiente">Siguiente</button>






    </div>
</template>


<script>
import Perfil from "@/components/Perfil.vue";
export default {
    name: 'Perfiles',
    components: {
        Perfil
    },

    data(){
        return{
            perfiles: [1,2,3]
        }
    },

    methods:{
        Inicio(){
            this.$router.push('/')
        },
        
        Anterior(){
            this.$router.go(-1)
        },

        Siguiente(){
            this.$router.go(1)
        }
    }
}
</script>