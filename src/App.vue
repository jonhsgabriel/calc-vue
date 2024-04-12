<script>
export default {
  data() {
    return {
      num1: 0,
      num2: 0,
      operator: 'adicao',
      result: 0
    };
  },
  methods: {
    calculate() {
      switch (this.operator) {
        case 'adicao':
          this.result = parseFloat(this.num1) + parseFloat(this.num2);
          break;
        case 'subtracao':
          this.result = parseFloat(this.num1) - parseFloat(this.num2);
          break;
        case 'multiplicacao':
          this.result = parseFloat(this.num1) * parseFloat(this.num2);
          break;
        case 'divisao':
          this.result = parseFloat(this.num1) / parseFloat(this.num2);
          break;
        default:
          this.result = 0;
      }
    }
  }
};
</script>

<template>
<div class="container" id="app">
  <header class="p-5 mb-4 mt-4 bg-dark rounded-4" >
    <h1>Calculadora Aritmética</h1>
  </header>
    
    <div>
      <input type="number" v-model.number="num1" @input="calculate">
      <select v-model="operator" @change="calculate">
        <option value="adicao">+</option>
        <option value="subtracao">-</option>
        <option value="multiplicacao">*</option>
        <option value="divisao">/</option>
      </select>
      <input type="number" v-model.number="num2" @input="calculate">
      <span>= {{ result }}</span>
    </div>
</div>
</template>

<style scoped>
#app {
  text-align: center;
  margin-top: 50px;
}

input[type="number"] {
  width: 150px;
  padding: 5px;
  margin: 5px;
}

select {
  padding: 5px;
  margin:  5px;
}

span {
  font-weight: bold;
}
h1 {
  color: #fff;
}
</style>
