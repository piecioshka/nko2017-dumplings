<template>
  <section>
    <ul>
      <li v-for="answer in question.answers" :key="answer.id"
          @click="selectAnswer(answer)">
        <answers-list-element :answer="answer"></answers-list-element>
      </li>
    </ul>
  </section>
</template>

<script>
  import AnswersListElement from './answers-list-element.vue';

  export default {
    name: 'AnswersList',
    props: {
      question: Object
    },
    components: {
      AnswersListElement
    },
    methods: {
      selectAnswer(a) {
        this.$emit('selectAnswer', a)
      }
    }
  }
</script>

<style lang="scss" scoped>
</style>
