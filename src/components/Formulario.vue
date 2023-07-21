<script setup>
const props = defineProps(['pegaNum1','filtraQualConta', 'pegaNum2', 'trocarFiltro'])
</script>


<template>
    <form>
        <div class="row">
            <div class="col-md-5">
                <input @change="props.pegaNum1" type="number"
                    class="form-control text-center" required placeholder="Digite um numero">
            </div>
            <div class="col-md-1">
                <p v-if="props.filtraQualConta === 'adicao'" class="text-center m-0 p-0 fs-4">+</p>
                <p v-else-if="props.filtraQualConta === 'subtracao'" class="text-center m-0 p-0 fs-4">-</p>
                <p v-else-if="props.filtraQualConta === 'multiplicacao'" class="text-center m-0 p-0 fs-4">*</p>
                <p v-else="props.filtraQualConta === 'divisao'" class="text-center m-0 p-0 fs-4">/</p>
            </div>
            <div class="col-md-5">
                <input @keyup="props.pegaNum2" type="number"
                    class="form-control text-center" required placeholder="Digite um numero">
            </div>
            <div class="col-md-1">
                <select @change="props.trocarFiltro" class="form-control">
                    <option value="adicao">Soma</option>
                    <option value="subtracao">Subtração <i class="bi bi-alarm"></i></option>
                    <option value="multiplicacao">Multiplicação</option>
                    <option value="divisao">Divisão</option>
                    <i className="icon bi-envelope"></i>
                </select>
            </div>
        </div>
    </form>
</template>