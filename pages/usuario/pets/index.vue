<template>
  <div>
    <headerUsuario />
    <div class = "container pt-5">
	    <div class = "mx-auto">
        <h1 class="text-center mb-5">Bem vindo! veja seus pets.</h1>
        <b-table striped hover :items="pets" :fields="campos">
          <template #cell(ações)="row">
            <b-button size="sm" class="mr-2" :to="'/usuario/pets/${row.item.id}'">
              Ver detelhes
            </b-button>
          </template>
        </b-table>
        <b-row class="mx-0 mt-2" style="width: auto; max-width: 150px;">
          <b-button size="sm" class="mr-2" alingh to="/usuario/pets/criar">
              Adicionar pet
            </b-button>
        </b-row>
	    </div>
    </div>
  </div>
</template>
<script>
import Header from '@/components/HeaderUsuario.vue'
import HeaderUsuario from '../../../components/HeaderUsuario.vue'
export default {
  components: { HeaderUsuario },
  name: 'Pets',
  data(){
    return{
      campos: [
        'nome','dono','Ações'
      ],
      pets: [
        {id: 1, nome: 'pandaBoy', dono : 'danilo'},
        {id: 2, nome: 'pituca', dono : 'joao'},
        {id: 3, nome: 'florzinha', dono : 'danilo'},
        {id: 4, nome: 'pandora', dono : 'henrique'},
      ]
    }
  }
}
</script>