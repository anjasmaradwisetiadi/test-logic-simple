<template>
  <section class="Dashbord">
    <div class="container">
      <div class="row justify-content-center">
        <div class="col-md-8">
          <div class="d-flex flex-column">
            <quiz-one></quiz-one>
            <quiz-two></quiz-two>
            <quiz-three></quiz-three>
            <quiz-four></quiz-four>
            <quiz-five></quiz-five>
            <quiz-six></quiz-six>
            <quiz-seven></quiz-seven>
            <quiz-eight></quiz-eight>
            <quiz-eleven></quiz-eleven>
            <quiz-ten></quiz-ten>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
<script>
  import quizOne from './quiz/quizOne.vue'
  import QuizThree from './quiz/quizThree.vue'
  import QuizTwo from './quiz/quizTwo.vue'
  import QuizFour from './quiz/quizFour.vue'
  import QuizSix from './quiz/quizSix.vue'
  import QuizSeven from './quiz/quizSeven.vue'
  import QuizEleven from './quiz/quizEleven.vue'
  import QuizTen from './quiz/quizTen.vue'
  import QuizFive from "./quiz/quizFive";
  import QuizEight from "./quiz/quizEight";

  export default {
    components: {
      QuizFive,
      quizOne,
      QuizTwo,
      QuizThree,
      QuizFour,
      QuizSix,
      QuizSeven,
      QuizEleven,
      QuizTen,
      QuizEight
    },

  }
</script>

<style scoped>

</style>
