<template>
  <div class="about">
    <!-- Check All -->
    <input type='checkbox' @click='checkAll()' v-model='isCheckAll'> Check All

    <!-- Checkboxes list -->
    <ul>
      <li v-for='lang in langsdata'>
        <input type='checkbox' v-bind:value='lang' v-model='languages' @change='updateCheckall()'>{{ lang }}
      </li>
    </ul>

    <!-- Print -->
    <input type='button' @click='printValues()' value='Print Selected Values'>

    <br>
    Selected items : {{ selectedlang }}
  </div>
</template>
<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue';
import Dashbord from '../components/Dashbord.vue';

export default {
  name: 'About',
  components: {
    HelloWorld,
    Dashbord
  },
  data(){
    return{
      isCheckAll: false,
      langsdata: ["PHP","Vue.js","AngularJS","jQuery","JavaScript"],
      languages: [],
      selectedlang: ""
    }
  },
  methods: {
    checkAll: function(){

      this.isCheckAll = !this.isCheckAll;
      this.languages = [];
      if(this.isCheckAll){ // Check all
        for (var key in this.langsdata) {
          this.languages.push(this.langsdata[key]);
        }
      }
    },
    updateCheckall: function(){
      if(this.languages.length === this.langsdata.length){
        this.isCheckAll = true;
      }else{
        this.isCheckAll = false;
      }
    },
    printValues: function(){
      this.selectedlang = "";
      // Read Checked checkboxes value
      for (var key in this.languages) {
        this.selectedlang += this.languages[key]+", ";
      }
    }
  }

};
</script>
