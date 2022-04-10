<template>
  <div>
    <headerUsuario/>
    <div class = "container pt-5">
	    <div class = "mx-auto">
        <h1 class="text-center mb-5">Bem vindo! veja seus pets.</h1>   
        <b-table striped hover label-sort-asc="" label-sort-desc="" label-sort-clear="" :items="pets" :fields="campos">
            <template  #cell(Ações)="row">
              <b-button size="sm" class="mr-2" :to="`/usuario/pets/${row.item.idPet}`">
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
export default {
  name: 'Pets',
  data(){
    return{
      campos: [
        {key: "name", sortable: true,label: "Nome"},
        {key: "dono.name", sortable: true, label: "Dono"},
        {key: "Ações", sortable: true, label: "Ações"},
      ],
      pets: []
    }
  },
  mounted(){
    this.consumirPets()
  },
  methods:{
    consumirPets(){
      this.$axios.get("/pet/buscar/")
      .then(res => {
        this.pets = res.data
      })
    }
  }
}
</script>