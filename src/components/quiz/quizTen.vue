<template>
  <div class="quizTen text-left mt-2">
    <b-button v-b-toggle.collapse-10 variant="primary">soal no.10</b-button>
    <b-collapse id="collapse-10" class="mt-2">
      <b-card>
        <p class="card-text">Input: {{dataIsi}}
          <br> penjumlahan = 7</p>
        <b-button v-b-toggle.collapse-10-inner size="sm">Hasil : </b-button>
        <b-collapse id="collapse-10-inner" class="mt-2">
          <b-card> hasil : {{displayData}}</b-card>
        </b-collapse>
      </b-card>
    </b-collapse>
  </div>
</template>
<script>
  export default {
    data() {
      return {
        dataIsi: [3, 5, 2, -4, 8, 11, 4, -1]
      }
    },
    computed: {
      displayData() {
        let data = this.dataIsi;
        let collectData = [];
        let reduceData = 0;

        data = data.sort(function (a, b) {
          return a - b
        })

        let hasilTrue = false
        for (let i = 0; i < data.length; i++) {
          for (let j = 0; j < data.length; j++) {
            if ((data[i] + data[j]) === 7)
              collectData.push([data[i], data[j]])
          }
        }

        reduceData=((collectData.length)/2)

        return collectData;
      }

    }
  }

</script>
<style lang="scss" scoped>

</style>
