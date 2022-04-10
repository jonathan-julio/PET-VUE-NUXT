<template>
  <div>
    <headerVeterinario/>
    <div class = "container pt-5">
	    <div class = "mx-auto">
        <h1 class="text-center mb-5">Consultas aceitas</h1>
        <b-table striped hover label-sort-asc="" :items="consultas" :fields="campos">
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
        {key: "veterinario.name", sortable: true, label: "Veterinario"}
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
        this.consultas = this.consultas.filter(c => c.status == 1)
       })
    },
  }
}
</script>