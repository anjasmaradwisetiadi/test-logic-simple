<template>
  <div class="quizEleven text-left mt-2">
    <b-button v-b-toggle.collapse-11 variant="primary">soal no.11</b-button>
    <b-collapse id="collapse-11" class="mt-2">
      <b-card>
        <p class="card-text">Buatlah program untuk mencari orang yang berusia di bawah 21 tahun dari JSON berikut ini</p>
        <b-button v-b-toggle.collapse-2-inner size="sm">Hasil</b-button>
        <b-collapse id="collapse-2-inner" class="mt-2">
          <b-card>
              <ul v-for="item in lookEmployee" :key="item.id">
                  <li>username : {{item}}  </li>
              </ul>
          </b-card>
        </b-collapse>
      </b-card>
    </b-collapse>
  </div>
</template>
<script>
import {dataEmployee} from '../../data/dataEmployee'

export default {

    computed:{
        lookEmployee(){
            let sortEmployee=[];
            const employee=dataEmployee.filter((value)=> value.age < 21 )
            employee.forEach(value =>{
                sortEmployee.push(value.name)
            })
            return sortEmployee
        }
    }
}
</script>
<style lang="scss" scoped>

</style>
