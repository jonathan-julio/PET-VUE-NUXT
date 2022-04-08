<template>
  <div>
    <div class = "container pt-5">
	    <div class = "mx-auto">
        <h1 class="text-center mb-5">Consultas</h1>
        <b-table striped hover :items="pets" :fields="campos">
          <template #cell(ações)="row">
          </template>
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
      campos: [
        'nome','estado','veterinario'
      ],
      pets: [
        {nome: 'pandaBoy',estado: 0, veterinario : 'danilo'},
        {nome: 'pituca',estado: 1,  veterinario : 'joao'},
        {nome: 'florzinha',estado: 2,  veterinario : 'danilo'},
        {nome: 'pandora', estado: 1, veterinario : 'henrique'},
      ]
    }
  }
}
</script>