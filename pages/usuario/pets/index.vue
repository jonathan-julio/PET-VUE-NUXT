<template>
  <div>
    <div class = "container pt-5">
	    <div class = "mx-auto mt-5">
        <h1 class="text-center">Bem vindo! veja seus pets.</h1>
        <b-table striped hover :items="pets">

        </b-table>
	    </div>
    </div>
  </div>
</template>
<script>
export default {
  name: 'Pets',
  data(){
    return{
      pets: [
        {nome: 'pandaBoy', dono : 'danilo'},
        {nome: 'pituca', dono : 'joao'},
        {nome: 'florzinha', dono : 'danilo'},
        {nome: 'pandora', dono : 'henrique'},
      ]
    }
  }
}
</script>