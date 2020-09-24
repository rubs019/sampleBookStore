<template>
  <form @submit.prevent="submitEvent(finalInput)">
    <b-field>
      <b-input
        placeholder="Search books"
        rounded
        v-model="finalInput"
        :value="finalInput"
      ></b-input>
    </b-field>
  </form>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  props: {
    input: String,
  },
  data() {
    return {
      finalInput: this.input,
    }
  },
  methods: {
    submitEvent(finalInput: String) {
      console.log('ok')
      this.$emit('submit', finalInput)
    },
  },
})
</script>

<style scoped>

</style>
