<template>
<div>
  <button type="button" @click="incCounter">Increment</button>
  <button type="button" @click="decCounter">decrement</button>
</div>
</template>

<script>
export default {
  methods: {
    incCounter() {
      this.$store.state.counter++
    },
    decCounter() {
      this.$store.state.counter--
    }
  }
}
</script>

<!-- So what if we have more getters
so vuex provide a features where we can access convineantly all getters without setting manually computed property
so vuex has helper function called mapGetters wo for that we need to import first to use it.
 -->
