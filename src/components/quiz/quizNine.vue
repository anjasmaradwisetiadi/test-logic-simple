<template>
  <div class="quizNine text-left mt-2">
    <b-button v-b-toggle.collapse-9 variant="primary">soal no.9</b-button>
    <b-collapse id="collapse-9" class="mt-2">
      <b-card>
        <p class="card-text">
          temukan rentang nilai kabisat dimana dengan mengisikan rentang 2 nilai di inputan dibawah
        </p>
        <b-button v-b-toggle.collapse-9-inner size="sm">Lihat Program</b-button>
        <b-collapse id="collapse-9-inner" class="mt-2">
          <b-card>
            <!-- pangkat -->
            <div class="row">
              <div class="col-4">
                <b-form-input
                  v-model.number="yearStart"
                  placeholder="masuakan nilai mu"
                ></b-form-input>
                <b-form-input
                  class="mt-2"
                  v-model.number="yearEnd"
                  placeholder="masukan nilai pangkat"
                ></b-form-input>
                <b-button
                  v-b-toggle.collapse-9-inner
                  size="sm"
                  class="btn btn-primary mt-2"
                  @click.prevent="countPangkat(yearStart, yearEnd)"
                >
                  Hasil
                </b-button>
                <b-collapse id="collapse-9-inner" class="mt-2">
                  <b-card>
                    <span v-for="item in resultLeap">{{ item }}, </span>
                  </b-card>
                </b-collapse>

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
  name: "quizNine",
  data(){
    return{
      yearStart:0,
      yearEnd:0,
      resultLeap:[]
    }
  },
  methods:{
    countPangkat(yearStart, yearEnd) {
      for (let year = yearStart; year < yearEnd; year++) {
        if ((0 == year % 4 && 0 != year % 100) || 0 == year % 400) {
          this.resultLeap.push(year)
        }
      }
    },
  }

}
</script>

<style scoped>

</style>
