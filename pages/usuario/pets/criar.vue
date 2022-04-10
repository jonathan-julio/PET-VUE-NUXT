<template >
  <div>
    <headerUsuario/>
        <div class="container pt-5" style="width: 30%; min-width: 300px;">
          <h2 class="text-center">Cadastre seu novo pet</h2>
          <hr>
          <b-form @submit.prevent="onSubmit">
              <b-form-group id="grupo1" label="Nome" label-for="input1" >
                <b-form-input id="input1" placeholder="Florzinha" v-model="form.name" required></b-form-input>
              </b-form-group>
              <b-form-group id="grupo2" label="Aniversario" label-for="input2">
                <b-form-input id="input2"  type="date" placeholder="Insira o aniversario do pet" v-model="form.d_niver" required></b-form-input>
              </b-form-group>
              <b-form-group id="grupo3" label="Dono" label-for="input3">
                <b-form-select id="input3"  :options="options" v-model="form.idDono" required ></b-form-select>
              </b-form-group>
  
              <b-button class="mt-2" type="submit" variant="primary">
                Adicionar
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
              name: '',
              d_niver: '',
              idDono: null
          },
          options:[
            {value: null, text: "Escolha o dono do pet"}
          ],
          donos: []
      }
  },
  mounted(){
    this.consumirDonos()
  },
  methods: {
    consumirDonos(){
      this.$axios.get("dono/buscar/")
      .then(res => {
        this.donos = res.data
        console.log(res.data)
        this.donos.forEach((value, index) => {
          this.options.push({
            value : value.idPessoa,
            text: value.name
          })
        })
      })
    },
      onSubmit(){
        this.$axios.post("pet/cadastrar/"+this.form.idDono,{
          d_niver :this.form.d_niver,
          name: this.form.name
        })
          console.log(this.form);
          this.$router.push("/usuario/pets");
      }
  }
}
</script>