<script setup>
import { reactive } from 'vue';
import Cabecalho from './components/Cabecalho.vue';
import Formulario from './components/Formulario.vue';
import Resultado from './components/Resultado.vue';

const estado = reactive({
  num1: 0,
  num2: 0,
  contas: 'adicao',

})

function soma() {
  const soma = estado.num1 + estado.num2
  const resultado = soma
  return resultado

}

function subtracao() {
  const soma = estado.num1 - estado.num2
  const resultado = soma
  return resultado

}

function multiplicacao() {
  const soma = estado.num1 * estado.num2
  const resultado = soma
  return resultado

}

function divisao() {
  const soma = estado.num1 / estado.num2
  const resultado = soma
  return resultado

}

const filtraconta = () => {
  const { contas } = estado

  switch(contas) {
    case 'subtracao':
      return subtracao()
    case 'multiplicacao':
      return multiplicacao()
    case 'divisao' :
      return divisao()
      default: 
        return soma() 
  }
}





</script>

<template>
  <div class="container">
    <Cabecalho />
    <Formulario :filtraQualConta="estado.contas"  :pegaNum1="evento => estado.num1 = parseFloat(Number(evento.target.value))" :pegaNum2="evento => estado.num2 = parseFloat(Number(evento.target.value))" :trocarFiltro="evento => estado.contas = evento.target.value"></Formulario> 
    <Resultado :filtracontas="filtraconta()"/>
    
    

  </div>
</template>


