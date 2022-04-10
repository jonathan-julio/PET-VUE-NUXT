<template >
      <div class="container pt-5" style="width: 30%; min-width: 300px;">
        <h1 class="text-center">Atualizar Informações </h1>
        <p class="text-center mt-4 mb-0">Edite os dados do seu pet</p>
        <hr class="mt-1">
        <b-form @submit.prevent="onSubmit">
            <b-form-group id="grupo1" label="Nome" label-for="input1" >
              <b-form-input id="input1" placeholder="Florzinha" v-model="form.name" required></b-form-input>
            </b-form-group>
            <b-form-group id="grupo2" label="Aniversario" label-for="input2">
              <b-form-input id="input2"  type="date" placeholder="Insira o aniversario do pet" v-model="form.d_niver" required></b-form-input>
            </b-form-group>
            <b-button class="mt-2" type="submit" variant="primary">
              Atualizar
            </b-button>
 
            <hr>
        </b-form>
      </div>
</template>

<script>
export default {
  name: 'Login',
  data(){
      return{
          form:{
              name: '',
              d_niver: '',
              dono : {
                idPessoa : 0
              }
          }
      }
  },
  mounted(){
    this.consumirPet()
  },
  methods:{
    consumirPet(){
      this.$axios.get(`pet/buscar/${this.$route.params.id}`)
      .then(res => {
        this.form = res.data
      })
      
    },
    onSubmit(){
      this.$axios.post("pet/cadastrar/" + this.form.dono.idPessoa, {
        idPet : this.$route.params.id,
        name :this.form.name,
        d_niver: this.form.d_niver
      }).then(res => {
        this.$router.push('/usuario/pets');
      });
    }
  }
}
</script>