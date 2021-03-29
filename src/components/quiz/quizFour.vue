<template>
  <div class="quizThree text-left mt-2">
    <b-button v-b-toggle.collapse-2 variant="primary">soal no.4</b-button>
    <b-collapse id="collapse-2" class="mt-2">
      <b-card>
        <p class="card-text">Collapse contents Here</p>
        <b-button v-b-toggle.collapse-2-inner size="sm">Toggle Inner Collapse</b-button>
        <b-collapse id="collapse-2-inner" class="mt-2">
          <b-card>Hello!</b-card>
        </b-collapse>
      </b-card>
    </b-collapse>
  </div>
</template>
<style lang="scss" scoped>

</style>
<script>
  export default {

  }

</script>
