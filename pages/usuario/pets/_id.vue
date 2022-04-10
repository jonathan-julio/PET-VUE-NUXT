<template>
  <div>
    <headerUsuario/>
    <div class = "container pt-5">
	    <b-button variant="primary" size="sm" class="mt-4 mb-2" :to="'/usuario/pets/'">
            Voltar aos Pets
        </b-button>
        <hr>
        <div class="mt-3 mb-5 ml-2 mr-2">
            <b-row>
                <b-col>
                    <b-row class="mt-2">
                        <h1 class="pt-2">{{pet.name}}</h1>
                    </b-row>
                    <b-row class="mt-2">
                        <span >Aniversario: {{pet.d_niver}}</span>
                    </b-row>
                    <b-row class="mt-2">
                        <span>Dono: {{pet.dono.name}}</span>
                    </b-row>
                    <b-row class="mt-1 mx-auto">
                        <b-button style="width: auto;" size="sm" class="ml-1"  to="consulta/1">
                            Solicitar consulta
                        </b-button>
                        <b-button style="width: auto;" size="sm" variant="warning" class="- mx-1"  :to="`editar/${pet.idPet}`">
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
      pet: {
        idPet : 0,
        name: '',
        d_niver : '',
        dono : {
          name : ''
          }
      },
    }
  },
  mounted(){
    this.consumirPet()
  },
  methods:{
    consumirPet(){
      this.$axios.get(`pet/buscar/${this.$route.params.id}`)
      .then(res => {
        this.pet = res.data,
        console.log(res.data)
      })
    },
      excluir(){
          this.$axios.delete(`pet/remover/${this.$route.params.id}`)
      .then(res => {
        this.$router.push('/usuario/pets')
      })
      }
  }
}
</script>