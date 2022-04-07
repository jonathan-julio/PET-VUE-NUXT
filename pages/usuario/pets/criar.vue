<template >
  <b-row class="mt-5" >
    <b-col sm="5" class="d-flex justify-content-center align-items-center ">
      <div class="col-8">
        <h2 class="text-center mb-3 title-login">Cadastre seu novo pet</h2>
        <hr>
        <b-form @submit.prevent="onSubmit">
            <b-form-group id="grupo1" label="Nome" label-for="input1" >
              <b-form-input id="input1" placeholder="Florzinha" v-model="form.Nome"></b-form-input>
            </b-form-group>
            <b-form-group id="grupo2" label="Aniversario" label-for="input2">
              <b-form-input id="input2"  type="date" placeholder="Insira o aniversario do pet" v-model="form.aniversario" ></b-form-input>
            </b-form-group>
            <b-form-group id="grupo3" label="Dono" label-for="input3">
              <b-form-input id="input3"  placeholder="Insira o dono do Pet" v-model="form.idDono" ></b-form-input>
            </b-form-group>
 
            <b-button class="mt-2" type="submit" variant="primary">
              Adicionar
            </b-button>
 
            <hr>
 
           
        </b-form>
      </div>
    </b-col>
    <b-col sm="9"></b-col>
  </b-row>
</template>

<script>
export default {
  name: 'Login',
  data(){
      return{
          form:{
              Nome: '',
              aniversario: '',
              idDono: 0
          }
      }
  },
  methods: {
      onSubmit(){
          console.log(this.form);
          this.$router.push("/usuario/pets");
      }
  }
}
</script>