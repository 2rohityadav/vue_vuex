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
      this.$emit('updated', 1);
    },
    decCounter() {
      this.$emit('updated', -1);
    }
  }
}
</script>
