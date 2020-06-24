<template>
  <div class="about">
    <h1>This is an about page</h1>
    <button @click="toastOpen">click</button>
  </div>
</template>

<script>
export default {
  methods: {
    toastOpen () {
      this.$toast.show('this is about')
    }
  }
}
</script>
