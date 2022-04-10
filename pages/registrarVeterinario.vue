<template>
<div>
  <b-button  style="margin-left: 5%;" variant="primary" size="sm" class="mt-4 mb-2" :to="'/'">
            Voltar a Tela de login
        </b-button>

      <div class="container pt-5" style="width: 30%; min-width: 300px;">
        
        <h2 class="text-center mb-3 title-login">Realizar cadastro</h2>
        <hr>
        <b-form @submit.prevent="onSubmit">
            <b-form-group label="Nome" label-for="nome" >
              <b-form-input id="input1" placeholder="jose" v-model="form.name" required></b-form-input>
            </b-form-group>
            <b-form-group label="Telefone" label-for="telefone" >
              <b-form-input id="input2" placeholder="(00) 00000-0000" v-model="form.telefone" required></b-form-input>
            </b-form-group>
            <b-form-group label="Endereço" label-for="endereco" >
              <b-form-input id="input2" placeholder="Rua da UF" v-model="form.endereco" required></b-form-input>
            </b-form-group>
            <b-form-group label="E-mail" label-for="email" >
              <b-form-input id="input2" placeholder="myPet@email.com" v-model="form.email" required></b-form-input>
            </b-form-group>
    
 
            <b-button class="mt-2" type="submit" variant="primary">
              Cadastrar
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
          form:{
              name:'',
              telefone: '',
              endereco:'',
              email: ''
          }
      }
  },
  methods: {
      onSubmit(){
          console.log(this.form);
          this.$axios.post("veterinario/cadastrar/", {
            name: this.form.name,
            email:this.form.email,
            telefone: this.form.telefone,
            endereco : this.form.endereco
          }).then(res=>{
            this.$router.push('/')
          }).catch(err => {
            console.log(err);
          })
      }
  }
}
</script>