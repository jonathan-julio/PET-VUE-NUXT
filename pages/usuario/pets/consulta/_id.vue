<template >
  <div>
    <headerUsuario/>
        <div class="container pt-5" style="width: 30%; min-width: 300px;">
          <h1 class="text-center">Insira os dados do seu pet</h1>
          <hr>
          <b-form @submit.prevent="onSubmit">
              <b-form-group id="grupo1" label="Data" label-for="input1">
                <b-form-input id="input1"  type="date" placeholder="Insira a data da consulta" v-model="form.d_consulta" required></b-form-input>
              </b-form-group>
              <b-form-group id="grupo2" label="Veterinario" label-for="input2">
                <b-form-select id="input2" v-model="veterinario" :options="opcoes" required>
            </b-form-select>
              </b-form-group>
              <b-button class="mt-2" type="submit" variant="primary">
                Consultar
              </b-button>
  
              <hr>
  
            
          </b-form>
        </div>
  </div>
</template>

<script>
export default {
  name: 'Login',
  data(){
      return{
          veterinario: null,
          vet: [],
          form:{
              d_consulta: '',
              status: 0
          },
          opcoes:[
            {value: null, text: "Escolha o veterinario"},
          ]
      }
  },
  mounted(){
    this.consumirVets()
  },
  methods:{
    consumirVets(){
      this.$axios.get(`veterinario/buscar/`)
      .then(res => {
        this.vets = res.data
        this.vets.forEach((value, index) => {
          this.opcoes.push({
            value: value.idPessoa,
            text: value.name
          })
        })
      })
      
    },
    onSubmit(){
      this.$axios.post("consulta/cadastrar/" + this.$route.params.id + "/" + this.veterinario,{
        d_consulta: this.form.d_consulta,
        status: this.form.status
        })
        this.$router.push("/usuario/pets");
    }
  }
}
</script>