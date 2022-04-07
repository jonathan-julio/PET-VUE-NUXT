<template>
  <b-row class="mt-5 ">
    <b-col sm="5" class="d-flex justify-content-center align-items-center ">
      <div class="col-8">
        <h2 class="text-center mb-3 title-login">Faça o login</h2>
        <hr>
        <b-form @submit.prevent="onSubmit">
            <b-form-group label="E-mail" label-for="email" >
              <b-form-input id="input1" placeholder="myPet@email.com" v-model="form.email"></b-form-input>
            </b-form-group>
            <b-form-group label="Senha" label-for="password">
              <b-form-input id="password"  type="password" placeholder="Digite sua senha" v-model="form.password" ></b-form-input>
            </b-form-group>
 
            <b-button class="mt-2" type="submit" variant="primary">
              Entrar
            </b-button>
 
            <hr>
 
           
        </b-form>
      </div>
    </b-col>
    <b-col sm="9"></b-col>
  </b-row>
</template>

<script>
//import bootstrap from '../node_modules/bootstrap/dist/css/bootstrap.css';
export default {
  name: 'Login',
  data(){
      return{
          form:{
              email: '',
              password: ''
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