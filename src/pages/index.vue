<template>
  <div class="container">
    <div>
      <Logo />
      <h1 class="title">Front Books</h1>
      <b-button @click="$router.push('create')">Ajouter</b-button>
      <b-button @click="getBooks">Refresh</b-button>
      <div class="form">
        <BaseInput @submit="getBook" />
      </div>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import BaseInput from '~/components/BaseInput.vue'

export default Vue.extend({
  components: {
    BaseInput,
  },
  data() {
    return {
      inputValue: null,
    }
  },
  methods: {
    async getBooks() {
      try {
        const books = await this.$axios.get('http://localhost:3092/books')
        console.log('books', books)
      } catch (err) {
        console.error(err)
      }
    },
    async getBook(title: String) {
      try {
        const book = await this.$axios.get(
          'http://localhost:3092/book?q=' + title
        )

        console.log('book', book)
      } catch(err) {
        console.error(err)
      }
    },
    cleanInput() {
      this.inputValue = null
    },
  },
})
</script>

<style>
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}

.title {
  font-family: 'Quicksand', 'Source Sans Pro', -apple-system, BlinkMacSystemFont,
    'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  display: block;
  font-weight: 300;
  font-size: 100px;
  color: #35495e;
  letter-spacing: 1px;
}

.subtitle {
  font-weight: 300;
  font-size: 42px;
  color: #526488;
  word-spacing: 5px;
  padding-bottom: 15px;
}

.links {
  padding-top: 15px;
}
</style>
