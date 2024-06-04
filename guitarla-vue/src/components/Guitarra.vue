<script setup>
import {onUpdated, ref} from "vue";

const numero = ref(0)


const props = defineProps({
    guitarra: { //definir prop
      type: Object,
      required: true
    }
  })

const updateCount = () => {
  alert("You make a click")
  numero.value = numero.value+1
}


</script>

<template>
  <!-- uso de la directiva v-for para crear varios elementos con la informacion de guitarras -->
  <div class="col-md-6 col-lg-4 my-4 row align-items-center">
    <div class="col-4">
      <img
          class="img-fluid"
          :src="'./img/' + guitarra.imagen + '.jpg'"
          :alt="'imagen guitarra' + guitarra.nombre"
      >
    </div>
    <div class="col-8"> <!-- acceso a las propiedades del objeto de la directiva de vue -->
      <h3 class="text-black fs-4 fw-bold text-uppercase">{{ guitarra.nombre }}</h3>
      <p>
        {{ numero }}
      </p>
      <p>
        {{ guitarra.descripcion }}
      </p>
      <p class="fw-black text-primary fs-3">
        {{ guitarra.precio }}
      </p>
      <button
          type="button"
          class="btn btn-dark w-100 "
          v-on:click=" updateCount() "
      >Agregar al Carrito</button>
    </div>
  </div><!-- FIN GUITARRA -->
</template>

<style scoped>

</style>