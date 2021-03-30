<template>
  <div class="quizFour text-left mt-2">
    <b-button v-b-toggle.collapse-4 variant="primary">soal no.4</b-button>
    <b-collapse id="collapse-4" class="mt-2">
      <b-card>
        <p class="card-text">Buatlah program untuk menentukan suatu kata atau kalimat merupakan
          palindrom atau bukan : </p>
        <b-button v-b-toggle.collapse-4-inner size="sm">Hasil : </b-button>
        <b-collapse id="collapse-4-inner" class="mt-2">
          <b-card>
            <ul v-for="(item,index) in data" :key="index">
              <li>kata {{item}} termasuk palindrom {{palindromWord}}</li>
            </ul>
          </b-card>
        </b-collapse>
      </b-card>
    </b-collapse>
  </div>
</template>
<style lang="scss" scoped>

</style>
<script>
  export default {
    data() {
      return {
        data: [
          "Radar",
          "Malam",
        ]
      }
    },

    computed: {
      palindromWord() {
        let statePalindrom = '';
        for ( let item of this.data) {
          var len = item.length;
          var mid = Math.floor(len / 2);

          for (var i = 0; i < mid; i++) {
            if (item[i] !== item[len - 1 - i]) {
              return statePalindrom="bukan palindrom";
            }
          }

          return statePalindrom="palindrom";
        }
      return statePalindrom;
      }
    }
  }

</script>
