<template>
  <div class="quizFour text-left mt-2">
    <b-button v-b-toggle.collapse-4 variant="primary">soal no.4</b-button>
    <b-collapse id="collapse-4" class="mt-2">
      <b-card>
        <p class="card-text">Buatlah program untuk menentukan suatu kata atau kalimat merupakan
          palindrom atau bukan : </p>
        <b-button v-b-toggle.collapse-4-inner size="sm" @click="handlePalindrom">Hasil : </b-button>
        <b-collapse id="collapse-4-inner" class="mt-2">
          <b-card>
            <ul v-for="(item,index) in resultPalindrom" :key="index">
              <li>{{item}}</li>
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
          "radar",
        ],
        resultPalindrom:[]
      }
    },

    computed: {
      palindromWord: function () {
        let statePalindrom = '';
        for (let item of this.data) {
          let len = item.length;
          let wordlower = item.toLowerCase()
          let mid = Math.floor(len / 2);

          for (let i = 0; i < mid; i++) {
            if (wordlower[i] !== wordlower[len - 1 - i]) {
              return statePalindrom = "bukan palindrom";
            }
          }

          return statePalindrom = "palindrom";
        }
        return statePalindrom;
      }
    },
    methods:{
      handlePalindrom(){
        for(let item of this.data){
          console.log('item', item)
          let statusPalindrom = ''
          let itemLength = item.length;
          let itemLowerCase= item.toLowerCase();


          for(let i =0; i<itemLength ; i++){
            if(itemLowerCase[i] !== itemLowerCase[itemLength-1-i]){
              statusPalindrom = `kata ${item} adalah Bukan Palindrom`
              return this.resultPalindrom.push(statusPalindrom)
            }
            statusPalindrom =  statusPalindrom = `kata ${item} adalah Palindrom`
            return this.resultPalindrom.push(statusPalindrom)
          }
        }
      }
    }
  }

</script>
