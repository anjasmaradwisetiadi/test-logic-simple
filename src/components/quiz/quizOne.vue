<template>
  <div class="quizOne text-left mt-2">
    <b-button v-b-toggle.collapse-1 variant="primary">soal no.1</b-button>
    <b-collapse id="collapse-1" class="mt-2">
      <b-card>
        <p class="card-text"> Buatlah program yang dapat menentukan grade dari suatu masukan angka,
          dengan kriteria
          sebagai berikut:</p>
        <ol class="text-left mt-2">
          <li v-for="(data,index) in termQuestions" :key="index"> {{data}} </li>
        </ol>
        <b-button v-b-toggle.collapse-1-inner size="sm">Hasil </b-button>
        <b-collapse id="collapse-1-inner" class="mt-2">
          <b-card>
            <b-form-input v-model="value" placeholder="Enter your Value"></b-form-input>
            <div class="mt-2">Huruf: {{ result }}</div>
          </b-card>
        </b-collapse>
      </b-card>
    </b-collapse>
  </div>
</template>
<style scoped>

</style>
<script>
  export default {
    data() {
      return {
        termQuestions: [
          "Jika angka lebih besar atau sama dengan 90, maka output adalah huruf A",
          "Jika angka di antara 80 dan 89, maka output adalah huruf B",
          "Jika angka di antara 70 dan 79, maka output adalah huruf C",
          "Jika angka di antara 60 dan 69, maka output adalah huruf D",
          "Jika angka lebih kecil dari pada 59, maka output adalah huruf E"
        ],
        value: null
      }
    },
    computed: {
      result() {
        let stateValue = null;
        if (this.value >= 90) {
          stateValue = 'A'
        } else if (this.value >= 80 && this.value <= 89) {
          stateValue = 'B'
        } else if (this.value >= 70 && this.value <= 79) {
          stateValue = 'C'
        } else if (this.value >= 60 && this.value <= 69) {
          stateValue = 'D'
        } else if (this.value >= 59) {
          stateValue = 'E'
        } else {
          stateValue = null
        }
        return stateValue;

      }
    }
    // methods: {

    // }
  }

</script>
