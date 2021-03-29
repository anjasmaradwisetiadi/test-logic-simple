<template>
  <div class="quizTwo mt-2 text-left">
    <b-button v-b-toggle.collapse-2 variant="primary">soal no.2</b-button>
    <b-collapse id="collapse-2" class="mt-2">
      <b-card>
        <p class="card-text">Buatlah program fungsi untuk menentukan suatu bilangan merupakan
          bilangan ganjil atau genap.</p>
        <b-button v-b-toggle.collapse-2-inner size="sm">Hasil </b-button>
        <b-collapse id="collapse-2-inner" class="mt-2">
          <b-card>
            <b-form-input v-model="value" placeholder="Enter your Value"></b-form-input>
            <div class="mt-2">Huruf: {{ result }}</div>
          </b-card>
        </b-collapse>
      </b-card>
    </b-collapse>
  </div>
</template>
<script>
  export default {
      data(){
          return{
              value:null,
          }
      },
      computed:{
          result(){
              let stateValue="";
              stateValue = (this.value%2 != 0) ? 'ganjil' : 'genap'
              return stateValue
          }
      }
  }

</script>
<style lang="scss" scoped>

</style>
