<template>
  <div class="calculadora">
  <input v-model="numero1" type="number" />
  <select v-model="operacao">
      <option value="+">+</option>
      <option value="-">-</option>
      <option value="*">*</option>
      <option value="/">/</option>
  </select>
  <input v-model="numero2" type="number" />
  <p :class="{ negativo: calcularResultado() < 0, positivo: calcularResultado() >= 0 }">Resultado: {{ calcularResultado() }}
</p>
  </div>
</template>

<script>
export default {
  data() {
  return {
      numero1: 0,
      numero2: 0,
      operacao: '+',
  };
  },
  methods: {
  calcularResultado() {
      switch (this.operacao) {
      case '+':
          return this.numero1 + this.numero2;
      case '-':
          return this.numero1 - this.numero2;
      case '*':
          return this.numero1 * this.numero2;
      case '/':
          return this.numero1 / this.numero2;
      default:
          return 0;
      }
  },
  },
};
</script>

<style scoped>
.calculadora {
  background-color: #dcdbdb; 
  border-radius: 10px; 
  box-shadow: 0px 4px 10px rgba(0, 0, 0, 0.1); 
  padding: 20px;
  margin-left: auto;
margin-right: auto;
width: 300px; 
align-items: center;
}

input[type="number"] {
  margin: 10px 0;
  padding: 10px;
  border: none;
  border-radius: 5px;
  width: calc(100% - 22px); 
}

select {
padding: 10px;
border-radius: 5px;
margin: 0 auto; 
margin-bottom: 10px;
}

  


p {
  margin-top: 10px;
}

input[type="number"]:focus,
select:focus {
  outline: none;
  box-shadow: inset 0px 0px 5px rgba(0, 0, 0, 0.2);
}

.positivo {
  color: green;
}
.negativo {
  color: red;
}

</style>

