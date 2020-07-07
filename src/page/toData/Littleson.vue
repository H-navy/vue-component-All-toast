<template>
    <div>
        <div class="Littleson">
            <h1>兄弟元素之间的互相点击事件</h1>
            <h2>{{msg}}</h2>
            <label for="">LittleNum: </label><span>{{num}}</span>
            <button @click="handle">点击</button>
        </div>
    </div>
</template>

<script>
import bus from './bus'
export default {
    data() {
        return {
            msg: '我是子元素中的小弟',
            num: 0
        }
    },
    methods: {
        handle: function() {
            bus.$emit('big-event', 2)
        }
    },
    mounted() {
        bus.$on('little-event', (val) => {
            this.num += val
        })
    }
}

</script>

<style scoped>
.Littleson{
    margin-top: 20px;
    border: 1px solid red;
    padding: 20px;
}
button{
    margin-left: 15px;
}
</style>
