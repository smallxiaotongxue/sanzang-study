<template>
  <div class="counter-warp">
    <p>Vuex counter：{{ count }}</p>
    <p>
      <button @click="increment">+</button>
      <button @click="decrement">-</button>
    </p>
  </div>
</template>

<script>
// Use Vuex
import index from '../../store/index'

export default {
  computed: {
    count () {
      return index.state.count
    }
  },
  methods: {
    increment () {
      index.commit('increment')
    },
    decrement () {
      index.commit('decrement')
    }
  }
}
</script>

<style>
.counter-warp {
  text-align: center;
  margin-top: 100px;
}
</style>
