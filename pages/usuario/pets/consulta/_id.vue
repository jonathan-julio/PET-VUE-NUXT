<template >
      <div class="container pt-5" style="width: 30%; min-width: 300px;">
        <h1 class="text-center">Insira os dados do seu pet</h1>
        <hr>
        <b-form @submit.prevent="onSubmit">
            <b-form-group id="grupo1" label="Data" label-for="input1">
              <b-form-input id="input1"  type="date" placeholder="Insira a data da consulta" v-model="form.data" required></b-form-input>
            </b-form-group>
            <b-form-group id="grupo2" label="Veterinario" label-for="input2">
              <b-form-select id="input2" v-model="form.veterinario" :options="opcoes" required>
          </b-form-select>
            </b-form-group>
            <b-button class="mt-2" type="submit" variant="primary">
              Consultar
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
          veterinario: null,
          form:{
              data: ''
          },
          opcoes:[
            {value: null, text: "Escolha o veterinario"},
            {value: 1, text: "Marcos"},
            {value: 2, text: "Debby"}
          ]
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