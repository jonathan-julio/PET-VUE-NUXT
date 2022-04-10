<template>
<div>
  <headerLogin/>
      <div class="container pt-5" style="width: 30%; min-width: 300px;">
        <h2 class="text-center mb-3 title-login" style="font-size: 30px;">Faça o login como veterinario</h2>
        <hr>
        <b-form @submit.prevent="onSubmit">
            <b-form-group label="E-mail" label-for="email" >
              <b-form-input id="input1" placeholder="myPet@email.com" v-model="form.email" required></b-form-input>
            </b-form-group>
 
            <b-button class="mt-2" type="submit" variant="primary">
              Entrar
            </b-button>
            
            <hr>
        </b-form>
        <a><nuxt-link to="/registrarVeterinario"> Cadastre-se</nuxt-link></a>
      </div>
</div>
</template>

<script>
export default {
  name: 'Login',
  data(){
      return{
          form:{
              email: ''
          }
      }
  },
  methods: {
      onSubmit(){
          console.log(this.form);
          this.$router.push("/veterinario/abertas");
      }
  }
}
</script>