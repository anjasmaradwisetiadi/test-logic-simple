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
            <div class="border">
                <input type="text" v-model="word">
                <button class="btn btn-primary mt-2" @click="dataWord()"> hasil</button>
            </div>
            <div class="border">
                <textarea type="text" v-model="wordTextArea">
                </textarea>
                <button class="btn btn-primary mt-2" @click="dataList()"> hasil</button>
            </div>

            <p> nilai yang dibalikan : {{resultReverseWord}}</p>
            <p class="mt-4"> nilai yang addList : {{resultAddList}}</p>
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
        wordTextArea:"",
        resultReverseWord:' ',
        resultAddList:""

      }
    },

    methods: {
      dataWord() {
        const data=this.word.split(' ');
        const valueWord=data.reverse();
        const joinWword=valueWord.join(' ');
        this.resultReverseWord=joinWword
      },
      dataList(){
        const dataAddList=[]
        const data=this.wordTextArea.split("\n");
        data.forEach(item=>{
          dataAddList.push("- "+item)
        })
        const joinAddList=dataAddList.join("\n")
        this.resultAddList=joinAddList
      }
    }
  }

</script>
<style lang="scss" scoped>

</style>
