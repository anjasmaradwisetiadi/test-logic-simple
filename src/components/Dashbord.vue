<template>
  <section class="Dashbord">
    <div class="container">
      <div class="row justify-content-center">
        <div class="col-md-8">
            <quiz-one></quiz-one>
        </div>
      </div>
    </div>
  </section>
</template>
<script>
import quizOne from './quiz/quizOne.vue'
  export default {
  components: { quizOne },

  }

</script>

<style scoped>

</style>
