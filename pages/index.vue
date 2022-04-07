<template>
  <div>
    <div class = "container pt-5">
	    <div class = "mx-auto mt-5">
        <h1>Bem vindo! Faça login para continuar.</h1>
        <b-row class = "mx-auto" style="width: 200px;" align-h = "center">
          <b-button variant = "info" size = "sm" class = "btn btn-primary btn-sm" to = "/loginUsuario">
            Área do Usuario!
          </b-button>
        </b-row> 
	    </div>
    </div>
  </div>
</template>

<script>
//import bootstrap from '../node_modules/bootstrap/dist/css/bootstrap.css';
export default {
  name: 'IndexPage'
}
</script>
