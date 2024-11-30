<script setup>
  import { reactive } from 'vue';
  import Cabecalho from './components/Cabecalho.vue';
  import Calculadora from './components/Calculadora.vue';

  const estado = reactive({
    operador: 'mais',
    valor1: 0,
    valor2: 0,
    resultado: 0
  })

  const editaValor1 = (evento) => {
    estado.valor1 = Number(evento.target.value);
    efetuaCalculo();
  }

  const editaValor2 = (evento) => {
    estado.valor2 = Number(evento.target.value);
    efetuaCalculo();
  }

  const trocarOperador = (evento) => {
    estado.operador = evento.target.value;
    efetuaCalculo();
  }

  const efetuaCalculo = () => {
    const { operador } = estado;
    switch (operador) {
      case 'menos':
        estado.resultado = estado.valor1 - estado.valor2;
        break;
      case 'vezes':
        estado.resultado = estado.valor1 * estado.valor2;
        break;
      case 'dividir':
        estado.resultado = estado.valor1 / estado.valor2;
        break;
      default:
        estado.resultado = estado.valor1 + estado.valor2;
    }
  }
</script>

<template>
  <div class="container">
    <Cabecalho />
    <Calculadora :valor1="estado.valor1" :valor2="estado.valor2" :trocar-operador="trocarOperador" :edita-valor1="editaValor1" :edita-valor2="editaValor2" :resultado="estado.resultado" />
  </div>
</template>