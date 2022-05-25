<template>
  <div class="quizFive text-left mt-2">
    <b-button v-b-toggle.collapse-5 variant="primary">soal no.5</b-button>
    <b-collapse id="collapse-5" class="mt-2">
      <b-card>
        <p class="card-text">Buatlah program untuk menentukan Fizz Buzz </p>
        <b-button v-b-toggle.collapse-5-inner size="sm">Lihat Program</b-button>
        <b-collapse id="collapse-5-inner" class="mt-2">
          <b-card>
            <!-- pangkat -->
            <div class="row">
              <div class="col-4">
                <b-form-input v-model.number="rangeFirst" placeholder="masuakan nilai mu"></b-form-input>
                <b-form-input class="mt-2" v-model.number="rangeEnd" placeholder="masukan nilai pangkat"></b-form-input>
                <button class="btn btn-primary mt-2" @click="countFizBuzz(rangeFirst,rangeEnd)"> Hasil </button>
              </div>
              <div class="col-8">
                <div class="">Value:</div>
                <div class="d-flex">
                  <span v-for="item in collectReuslt">{{ item }}</span>
                </div>
              </div>
            </div>
          </b-card>
        </b-collapse>
      </b-card>
    </b-collapse>
  </div>
</template>

<script>
export default {
  name: "quizFive",
  data(){
    return{
      rangeFirst: 0,
      rangeEnd:0,
      collectReuslt: []
    }
  },
  methods:{
    countFizBuzz(first, end){
      for(let x = first; x<end;x++){
        if (((x % 5)=== 0) && ((x % 3)===0)){
          this.collectReuslt.push('Fizz Buzz, ')
        } else if(x % 3 === 0 ){
          this.collectReuslt.push('Fizz, ')
        }else if(x % 5 === 0){
          this.collectReuslt.push('Buzz, ')
        }  else {
          this.collectReuslt.push(x,', ')
        }
      }
    }
  }
}
</script>

<style scoped>

</style>
