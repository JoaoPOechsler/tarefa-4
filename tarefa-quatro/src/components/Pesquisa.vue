<template>
  <fieldset>
    <h1>Consultar Placas</h1>
    <label for="placa">Placa:</label>
    <input type="text" id="placa" maxlength="8" v-model="placa" />
    <button @click="pesquisarVeiculo">Buscar</button>
    <img src="https://i0.statig.com.br/bancodeimagens/1y/k2/gh/1yk2ghfzz93cwo4zu0nwp508s.jpg" alt="placa de carro">
  </fieldset>
</template>

<script>
export default {
  data: function() {
    return {
      placa: ""
    };
  },
  methods: {
    pesquisarVeiculo: function() {       
      this.$store.state.infracoesVeiculo = this.$store.state.multas.filter(
        multa => multa.PLACA == this.placa
      );
      this.$router.push("/infracoes")
    }
  }
};
</script>

<style>
html, body{
  background: rgb(71, 134, 207);
}
fieldset{
width: 500px;
height: 380px;
margin: 40px 30%;
text-align: center;
border-radius: 10px;
border-color: black;
background:  rgb(71, 131, 187);
}
button{
  border-radius: 2px;
  background: rgb(71, 131, 187);
  margin: 0 10px;
}
label{
  margin: 0 10px;
}
input{
  border-radius: 2px;
  width: 150px;
  background:  rgb(71, 131, 187);
}
img {
  border: black 2px;
  margin: 55px 30px 6px 35px;
  width: 260px;
  height: 175px;
}
</style>