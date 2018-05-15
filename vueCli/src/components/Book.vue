<template>
  <div class="book" @click='chooseBook(ISBN)'>
    <h1>{{ name }}</h1>
    <p>{{author}}</p>
    <p>{{price}}</p>
    <p>{{ISBN}}</p>
    <slot></slot>
  </div>
</template>

<script>
export default {
  name: 'Book',
  props: {
    name: {
      type: String,
      require: true
    },
    author: {
      type: String,
      require: true
    },
    price: {
      type: Number,
      default: 100
    },
    ISBN: {
      type: String,
      require: true,
      validator (value) {
        return ['1', '2', '3'].indexOf(value) !== -1
      }
    }
  },
  data () {
    return {
    }
  },
  methods: {
    chooseBook (ISBN) {
      this.$emit('ISBN', ISBN)
    }
  },
  mounted () {
    // console.log(this.$root)
  }
}
</script>

<style scoped>
.book{
    display: inline-block;
    border: 1px solid #f0f0f0;
    background: #f0f00f;
    vertical-align: top;
}
</style>
