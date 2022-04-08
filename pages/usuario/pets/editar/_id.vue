<template >
      <div class="container pt-5" style="width: 30%; min-width: 300px;">
        <h1 class="text-center">Atualizar Informações </h1>
        <p class="text-center mt-4 mb-0">Edite os dados do seu pet</p>
        <hr class="mt-1">
        <b-form @submit.prevent="onSubmit">
            <b-form-group id="grupo1" label="Nome" label-for="input1" >
              <b-form-input id="input1" placeholder="Florzinha" v-model="form.Nome" required></b-form-input>
            </b-form-group>
            <b-form-group id="grupo2" label="Aniversario" label-for="input2">
              <b-form-input id="input2"  type="date" placeholder="Insira o aniversario do pet" v-model="form.aniversario" required></b-form-input>
            </b-form-group>
            <b-form-group id="grupo3" label="Dono" label-for="input3">
              <b-form-input id="input3"  placeholder="Insira o dono do Pet" v-model="form.idDono" required ></b-form-input>
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