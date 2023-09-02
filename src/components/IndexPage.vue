<template>
  <div class="container mt-5">
    <h1 class="text-primary bg-light p-3 rounded">Informe de Contrato</h1>

      <div class="row mt-4 justify-content-center">
        <div class="col-md-3 text-center">
          <label class="label-control" for="numero">ID del Contrato:</label>
        </div>
        <div class="col-md-3 text-center">
          <input type="number" class="form-control" id="numero" min="0" v-model="contractId">
        </div>
        <div class="col-md-3 text-center">
          <button class="btn btn-primary" v-on:click="prueba">Buscar</button>
        </div>
      </div>


      <div class="row mt-4 justify-content-center">
        <div class="col-md-3 text-center">
          <label for="label1">Campo 1</label>
        </div>
        <div class="col-md-3 text-center">
          <input type="text" class="form-control" id="label1">
        </div>
        <div class="col-md-3 text-center">
          <label for="label2">Campo 2:</label>
        </div>
        <div class="col-md-3 text-center">
          <input type="text" class="form-control" id="label2">
        </div>
      </div>
  </div>
</template>

<script>

export default {
  data() {
    return {
      contractId: 0,
      contract: null
    };
  },
  methods: {
    prueba(){
      fetch('https://localhost:7232/api/Contract/GetContractById?id='+this.contractId)
      .then((response) =>{ 
        response.json()
      });
    }
  },
};
</script>

<style scoped>
.btn {
  font-weight: bolder;
}

label {
  font-weight: bolder;
}
</style>
