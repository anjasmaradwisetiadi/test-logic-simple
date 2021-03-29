<template>
  <div class="quizThree text-left mt-2">
    <b-button v-b-toggle.collapse-3 variant="primary">soal no.3</b-button>
    <b-collapse id="collapse-3" class="mt-2">
      <b-card>
        <p class="card-text">Buatlah program untuk menentukan nilai maksimum, minimum, nilai tengah,
          dan rata-rata dari suatu deretan angka <br> Contoh : </p>
        <p class="card-text">-6, -4, 0, 1, 2, 2, 3, 10, 12, 44, 52, 72, 98</p>
        <b-button v-b-toggle.collapse-3-inner size="sm">Hasil</b-button>
        <b-collapse id="collapse-3-inner" class="mt-2">
          <b-card>
            <p> Min: {{getMin}}</p>
            <p> Max: {{getMax}}</p>
            <p> Median: {{getMedian}} </p>
            <p> Average: {{getAverage}}</p>
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
        value: [-6, -4, 0, 1, 2, 2, 3, 10, 12, 44, 52, 72, 98],
      }
    },

    computed: {
      getMin() {
        return Math.min(...this.value)
      },
      getMax() {
        return Math.max(...this.value)
      },

      getMedian() {
        const sorting = this.value.sort()
        console.log(sorting);
        const mid = Math.ceil(this.value.length / 2);
        const valueMedian = (mid % 2 != 0) ? (sorting[mid] + sorting[mid - 1]) / 2 : sorting[mid -
          1];
        return valueMedian
      },

      getAverage() {
        let average = 0;
        let count = 0;
        this.value.forEach(val => {
          count += val
        })
        average = count / this.value.length
        return average
      }
    }
  }

</script>
<style lang="scss" scoped>

</style>
