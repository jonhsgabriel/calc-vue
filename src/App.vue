<script setup>
  import {reactive} from 'vue';

  const estado = reactive({
    num1: 0,
    num2: 0,
    operator: 'soma',
    result: 0
  })

  function soma() {
    estado.result = estado.num1 + estado.num2;
    return estado.result;
  }

  const retorna = () => {
    const { operator } = estado;

    switch(operator){
      case 'soma':
        return soma();
    }
  }

</script>

<template>
<div class="container">
  <header class="p-5 mb-4 mt-4 bg-dark rounded-3">
    <h1>Calculadora</h1>
  </header>
  <form>
  <div class="row">
    <div class="col">
      <input @change="evento => estado.num1 = evento.target.value" type="number" placeholder="Digite um número" class="form-control">
    </div>
    <div class="col">
      <input @change="evento => estado.num2 = evento.target.value" type="number" placeholder="Digite um número" class="form-control">
    </div>
    <div class="col-md-2">
      <select @change="evento => estado.operator = evento.target.value" class="form-control">
        <option value="soma">Somar</option>
        <option value="subtração">Subtrair</option>
        <option value="divisão">Dividir</option>
        <option value="multiplicação">Multiplicar</option>
      </select>
    </div>
  </div>
</form>

<ul class="list-group mt-4 col-md-2">
  <li class="list-group-item">
    <label>Resultado {{ estado.result }}</label>
  </li>
</ul>
</div>
</template>

<style scoped>
h1 {
  color: #fff;
}
</style>
