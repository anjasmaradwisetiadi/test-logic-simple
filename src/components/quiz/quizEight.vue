<template>
  <div class="quizOne text-left mt-2">
    <b-button v-b-toggle.collapse-8 variant="primary"
    >soal no.8</b-button
    >
    <b-collapse id="collapse-8" class="mt-2">
      <b-card>
        <p class="card-text">
          Isikan 3 nilai dimana ketika ditambahkan mendekati nilai fibonanci
        </p>
        <div class="d-flex flex-column">
          <b-form-input class="col-4" v-model.number="inputOne" placeholder="Enter your Value"></b-form-input>
          <b-form-input class="col-4 mt-2" v-model.number="inputTwo" placeholder="Enter your Value"></b-form-input>
          <b-form-input class="col-4 mt-2" v-model.number="inputThree" placeholder="Enter your Value"></b-form-input>
        </div>
        <b-button
          v-b-toggle.collapse-8-inner
          size="sm"
          class="mt-2"
          @click.prevent="equalFibonancci"
        >Hasil
        </b-button>
        <b-collapse id="collapse-8-inner" class="mt-2">
          <b-card>
            <p>{{ this.resultFibonanci }}</p>
          </b-card>
        </b-collapse>
      </b-card>
    </b-collapse>
  </div>
</template>
<script>
let fibonanciData = [];

function fibonacci(value) {
  if (value === 0) {
    return 0;
  }
  if (value <= 2) {
    return 1;
  }
  return fibonacci(value - 1) + fibonacci(value - 2);
}

export default {
  name:'QuizEight',
  data() {
    return {
      value: null,
      valueFibonancci: [],
      dataCollect: [],
      inputOne: 0,
      inputTwo:0,
      inputThree:0,
      resultFibonanci:''
    };
  },
  methods: {
    equalFibonancci() {
      this.dataCollect.push(this.inputOne,this.inputTwo,this.inputThree)
      console.log('ini data collect = ', this.dataCollect)
      let sumDataCollect = 0;
      for (let i = 0; i < this.dataCollect.length; i++) {
        sumDataCollect += this.dataCollect[i];
      }
      const counts = fibonanciData;
      const output = counts.reduce((previous, curr) =>
        Math.abs(curr - sumDataCollect) < Math.abs(previous - sumDataCollect)
          ? curr
          : previous
      );
      const differentsial = output - sumDataCollect;
      if(differentsial === 0){
        this.resultFibonanci = 'ini nilai fibonanci'
      }else{
        this.resultFibonanci = `kurang ${differentsial} untuk mendekati nilai fibonanci ${output}`
      }
    },
  },

  mounted() {
    console.log(fibonacci(10));
    for (let i = 0; i < 10; i++) {
      fibonanciData.push(fibonacci(i));
    }
  },

  computed: {
    // dataFibonanci() {
    //   return fibonanciData.push(fibonacci(8));
    // },
  },
};
</script>

<style lang="scss" scoped>
</style>
