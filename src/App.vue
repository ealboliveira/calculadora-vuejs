<template>
  <div id="app" class="container mt-5">
    <h1>Calculadora Vue.js</h1>

    <div class="form-group">
      <label for="numero1">Número 1:</label>
      <input v-model="numero1" type="number" class="form-control" @input="calcularResultado" />
    </div>

    <div class="form-group">
      <label for="numero2">Número 2:</label>
      <input v-model="numero2" type="number" class="form-control" @input="calcularResultado" />
    </div>

    <div class="form-group">
      <label for="operacao">Operação:</label>
      <select v-model="operacao" class="form-control" @change="calcularResultado">
        <option value="soma">Soma (+)</option>
        <option value="subtracao">Subtração (-)</option>
        <option value="multiplicacao">Multiplicação (*)</option>
        <option value="divisao">Divisão (/)</option>
      </select>
    </div>

    <div class="form-group">
      <label for="resultado">Resultado:</label>
      <input :value="resultado" type="text" class="form-control" readonly />
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      numero1: 0,
      numero2: 0,
      operacao: 'soma',
      resultado: 0,
    };
  },
  methods: {
    calcularResultado() {
      switch (this.operacao) {
        case 'soma':
          this.resultado = this.numero1 + this.numero2;
          break;
        case 'subtracao':
          this.resultado = this.numero1 - this.numero2;
          break;
        case 'multiplicacao':
          this.resultado = this.numero1 * this.numero2;
          break;
        case 'divisao':
          this.resultado = this.numero1 / this.numero2;
          break;
      }
    },
  },
};
</script>

<style>
#app {
  max-width: 400px;
  margin: auto;
  text-align: center;
  background-color: #f5f5f5;
  padding: 20px;
  border-radius: 10px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
}

.form-group {
  margin-bottom: 15px;
}

h1 {
  color: #3498db;
}

select {
  width: 100%;
  padding: 10px;
  border: 1px solid #ccc;
  border-radius: 5px;
}

input[type="number"],
input[type="text"] {
  width: 100%;
  padding: 10px;
  border: 1px solid #ccc;
  border-radius: 5px;
  box-sizing: border-box;
}

input[type="text"] {
  font-weight: bold;
  color: #27ae60;
}

</style>
