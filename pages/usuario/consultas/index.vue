<template>
  <div>
    <headerUsuario/>
    <div class = "container pt-5">
	    <div class = "mx-auto">
        <h1 class="text-center mb-5">Consultas</h1>
        <b-table striped hover label-sort-asc=""
      label-sort-desc=""
      label-sort-clear=""
      :items="consultas" :fields="campos">
          <template #cell(status)="row">
            {{traduzirStatus(row.item.status)}}
          </template>
        </b-table>
	    </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Consultas',
  data(){
    return{
      campos:[
        'nome','estado','Veterinario'
      ],
      campos: [
        {key: "pet.name", sortable: true,label: "Nome"},
        {key: "d_consulta", sortable: true, label: "Data"},
        {key: "status", sortable: true, label: "Estado"},
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
       })
    },
    traduzirStatus(item){
    if(item == 0){
      return "Em aberto"
    }
    else if(item == 1){
      return "Aceita"
    }
    else {
      return "recusada"
    }
  }
  },
  
}
</script>