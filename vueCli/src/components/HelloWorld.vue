<template>
  <div class="hello">
    <Book name='javascript' author='nobody' :price='200' ISBN='1' @ISBN='getISBN'></Book>
    <Book name='javascript1' author='nobody' ISBN='2' @ISBN='getISBN'></Book>
    <Book name='javascript2' author='nobody' ISBN='3' @ISBN='getISBN'>与众不同</Book>
  </div>
</template>

<script>
import Book from './Book'
export default {
  name: 'HelloWorld',
  data () {
    return {
    }
  },
  components: {
    Book
  },
  methods: {
    getISBN (value) {
      console.log(value)
    }
  }
}
</script>

<style scoped>
</style>
