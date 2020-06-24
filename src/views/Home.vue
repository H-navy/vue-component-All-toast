<template>
  <div class="home">
    <h2>this is home page</h2>
    <button @click="toastOpen">click</button>
  </div>
</template>

<script>

export default {
  name: 'Home',
  methods: {
    toastOpen () {
      this.$toast.show('this is about')
    }
  }
}
</script>
