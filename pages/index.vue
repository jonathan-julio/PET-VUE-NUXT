<template>
  <div>
    <div class = "container pt-5">
	    <div class = "mx-auto mt-5">
        <h1 class="text-center">Bem vindo! Faça login para continuar.</h1>
        <b-row class = "mx-auto" style="width: 150px;" align-h = "center">
          <b-button variant = "info" size = "sm" class = "mr-2" to = "/loginUsuario">
            Área do Usuario!
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
