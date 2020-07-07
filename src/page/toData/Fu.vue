<template>
    <div>
        <h2>传值 父组件</h2>
        <h3>{{msg}}</h3>
        <button @click="parentResetbookname('穷查理宝典')">点击修改子组件中 读的书名</button>
        <Bigson :getFatherData="toSonData" ref="Bigson"></Bigson>
        <Little></Little>
    </div>
</template>

<script>
import Bigson from './Bigson'
import Little from './Littleson'
export default {
  components: {
    Bigson,
    Little
  },
  data() {
      return {
          msg: '我是父元素',
          // 要传给子元素的数据
          toSonData: {
              title: '这是要传给后代的数据',
              list: [1, 2, 3]
          }
      }
  },
  methods: {
      parentResetbookname: function(val) {
          this.$refs.Bigson.setVal(val)
      }
  }
}

</script>

<style scoped>
</style>
