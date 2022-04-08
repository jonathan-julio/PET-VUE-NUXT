<template>
  <div>
    <div class = "container pt-5">
	    <b-button variant="primary" size="sm" class="mt-4 mb-2" :to="'/usuario/pets/'">
            Voltar aos Pets
        </b-button>
        <hr>
        <div class="mt-3 mb-5 ml-2 mr-2">
            <b-row>
                <b-col>
                    <b-row class="mt-2">
                        <h1 class="pt-2">{{ pets[0].nome }}</h1>
                    </b-row>
                    <b-row class="mt-2">
                        <span >Aniversario: {{ pets[0].aniversario }}</span>
                    </b-row>
                    <b-row class="mt-2">
                        <span>Dono: {{ pets[0].dono }}</span>
                    </b-row>
                    <b-row class="mt-1 mx-auto">
                        <b-button style="width: auto;" size="sm" class="ml-1"  to="consulta/1">
                            Solicitar consulta
                        </b-button>
                        <b-button style="width: auto;" size="sm" variant="warning" class="- mx-1"  to="editar/1">
                            Editar
                        </b-button>
                        <b-button  style="width: auto;" size="sm" variant="danger" @click="excluir" class="ml-1">
                            Excluir
                        </b-button>
                    </b-row>
                </b-col>
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
        'nome','dono','Ações'
      ],
      pets: [
        {id: 1, nome: 'pandaBoy 2', dono : 'danilo', aniversario : '22-02-2020'},
        {id: 2, nome: 'pituca 2', dono : 'joao', aniversario: '20-02-2020'},
        {id: 3, nome: 'florzinha 2' , dono : 'danilo', aniversario: '18-02-2020'},
        {id: 4, nome: 'pandora 2', dono : 'henrique', aniversario: '16-02-2020'},
      ]
    }
  },
  methods:{
      excluir(){
          console.log("Elento excluido.");
      }
  }
}
</script>