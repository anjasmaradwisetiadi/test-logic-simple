<template>
  <div class="quizSeven text-left mt-2">
    <b-button v-b-toggle.collapse-7 variant="primary">soal no.7</b-button>
    <b-collapse id="collapse-7" class="mt-2">
      <b-card>
        <p class="card-text">Buatlah program untuk membalikkan "semua kata-kata" (bukan huruf) yang
          terdapat dalam suatu kalimat.</p>
        <b-button v-b-toggle.collapse-7-inner size="sm">program</b-button>
        <b-collapse id="collapse-7-inner" class="mt-2">
          <b-card>
            <input type="text" v-model="word">
            <button class="btn btn-primary mt-2" @click="dataWord()"> hasil</button>
            <p> nilai yang dibalikan : {{resultReverseWord}}</p>
          </b-card>
        </b-collapse>
      </b-card>
    </b-collapse>
  </div>
</template>
<script>
  export default {
    data() {
      return {
        word: ' ',
        resultReverseWord:' ',
      }
    },

    methods: {
      dataWord() {
        const data=this.word.split(' ');
        const valueWord=data.reverse();
        const joinWword=valueWord.join(' ');
        this.resultReverseWord=joinWword
      }
    }
  }

</script>
<style lang="scss" scoped>

</style>
