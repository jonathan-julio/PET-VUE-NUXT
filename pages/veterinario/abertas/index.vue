<template>
  <div>
    <headerVeterinario/>
    <div class = "container pt-5">
	    <div class = "mx-auto">
        <h1 class="text-center mb-5">Consultas abertas</h1>
        <b-table striped hover label-sort-asc="" :items="consultas" :fields="campos">
          <template #cell(ações)="row">
            <b-button size="sm" class="mr-2" @click="aceitarConsulta(row.item)">
              Aceitar
            </b-button>
            <b-button size="sm" class="mr-2" @click="recusarConsulta(row.item)">
              Recusar
            </b-button>
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
        {key: "pet.name", sortable: true,label: "Nome"},
        {key: "d_consulta", sortable: true,label: "Data"},
        {key: "veterinario.name", sortable: true, label: "Veterinario"},
        {key: "Ações", sortable: true, label: "Ações"},
      ],
      consultas: []
    }
  },
  mounted(){
    this.consumirConsultas()
  },
  methods:{
    consumirConsultas(){
      this.$axios.get("consulta/buscar/")
       .then(res => {
        this.consultas = res.data
        this.consultas = this.consultas.filter(c => c.status == 0)
       })
    },
    aceitarConsulta(item){
      this.$$axios.post("consulta/aprovar/"+item.idConsulta)
      .then(res => {
        this.consumirConsultas()
      })
    },
    recusarConsulta(item){
      this.$$axios.post("consulta/rejeitar/"+item.idConsulta)
      .then(res => {
        this.consumirConsultas()
      })
    },
  }
}
</script>