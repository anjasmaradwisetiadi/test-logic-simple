<template>
  <section class="Dashbord">
    <div class="container">
      <div class="row justify-content-center">
        <div class="col-md-8">
          <div class="d-flex flex-column">
            <quiz-one></quiz-one>
            <quiz-two></quiz-two>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
<script>
  import quizOne from './quiz/quizOne.vue'
  import QuizTwo from './quiz/quizTwo.vue'
  export default {
    components: {
      quizOne,
      QuizTwo
    },

  }

</script>

<style scoped>

</style>
