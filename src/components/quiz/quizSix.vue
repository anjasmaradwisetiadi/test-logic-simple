<template>
  <div class="quizSix text-left mt-2">
    <b-button v-b-toggle.collapse-6 variant="primary">soal no.6</b-button>
    <b-collapse id="collapse-6" class="mt-2">
      <b-card>
        <p class="card-text">Buatlah program rekursif. Anda bebas menentukan input dan output dari
          fungsi tersebut, tetapi harus rekursif.</p>
        <b-button v-b-toggle.collapse-6-inner size="sm">Lihat Program</b-button>
        <b-collapse id="collapse-6-inner" class="mt-2">
          <b-card>
            <!-- pangkat -->
            <div class="row">
              <div class="col-4">
                <b-form-input v-model.number="valuePangkat" placeholder="masuakan nilai mu"></b-form-input>
                <b-form-input v-model.number="pangkat" placeholder="masukan nilai pangkat"></b-form-input>
                <button class="btn btn-primary" @click="countPangkat(valuePangkat,pangkat)"> Hasil </button>
              </div>
              <div class="col-8">
                  <div class="">Value: {{ resultPangkat }}</div>
              </div>
            </div>
            <!-- rekrusif biasa -->
            <div class="row">
              <div class="col"></div>
            </div>
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
              valuePangkat:null,
              pangkat:null,
              resultPangkat:null
          }
      },

      methods:{
          countPangkat(valuePangkat, pangkat){
              if(pangkat === 0){
                  return this.resultPangkat=1
              }
              return this.resultPangkat= valuePangkat*this.countPangkat(valuePangkat, pangkat-1) 
          },
          countRekrusif(){
              
          }
      }
  }

</script>
<style lang="scss" scoped>

</style>
