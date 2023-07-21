<script setup>
const props = defineProps(['filtracontas'])
</script>

<template>
    <div class="row d-flex justify-content-center align-itemns-center mt-4">
        <div class="col-12">
          <div class="form-control text-center">
            <span>Resultado</span>
          </div>
        </div>
      </div>
      <div class="row mt-4">
        <div class="col">
          <p class="text-center text-success ">{{ props.filtracontas}}</p>
        </div>
      </div>
</template>

<style scoped>

.text-success {
  font-size: 100px;
}
</style>