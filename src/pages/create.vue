<template>
  <div>
    <Logo />
    <h1 class="title">Front Books</h1>
    <h2>Ajouter</h2>
    <div>
      <BaseInput @submit="submitForm" />
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  methods: {
    async submitForm(inputValue: string) {
      console.log('feu !', inputValue)
      try {
        await this.$axios.post('localhost:3092/books', { value: inputValue })
        this.cleanInput()
      } catch (err) {
        console.error(err)
      }
    },
  }
})
</script>

<style scoped lang="scss">

</style>
