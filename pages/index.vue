<template>
  <div>
    <div class = "container pt-5">
	    <div class = "mx-auto mt-5">
        <h1 class="text-center">Bem vindo! Faça login para continuar.</h1>
        <b-row class = "mx-auto"  align-h = "center">
          <b-button style="width: 150px;" variant = "info" size = "sm" class = "mx-2" to = "/loginUsuario">
            Área do Usuario!
          </b-button>
          <b-button style="width: 150px;" variant = "warning" size = "sm" to = "/loginVeterinario">
            Área do veterinario!
          </b-button>
        </b-row> 
	    </div>
    </div>
  </div>
</template>

<script>
import Header from '@/components/HeaderUsuario.vue';
export default {
  name: 'IndexPage'
}
</script>
