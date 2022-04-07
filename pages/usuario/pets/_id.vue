<template>
  <div>
    <div class = "container pt-5">
	    <b-button size="sm" class="mt-4 mb-2" :to="'/usuario/pets/'">
            Voltar aos Pets
        </b-button>
        <hr>
        <div class="mt-3 mb-5 ml-2 mr-2">
            <b-row>
                <b-col>
                    <b-row class="mt-2">
                        <h1 class="pt-2">{{ pets[0].nome }}</h1>
                    </b-row>
                </b-col>
            </b-row>
            <b-row>
                <b-col>
                    <b-row class="mt-2">
                        <span class="pt-2">Aniversario: {{ pets[0].aniversario }}</span>
                    </b-row>
                </b-col>
            </b-row>
            <b-row>
                <b-col>
                    <b-row class="mt-2">
                        <span class="pt-2">Dono: {{ pets[0].dono }}</span>
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
  }
}
</script>