<template>
    <div>
        <div class="Bigson">
            <h1>父元素向子元素传值</h1>
            <h2>{{getFatherData.title}}</h2>
            <ul>
                <li v-for="(item, index) in getFatherData.list" :key="index">
                    {{item}}
                </li>
            </ul>
            <label for="">BigsonNum: </label><span>{{num}}</span>
            <button @click="handle">点击</button>
            <div>我最近在对这本书{{bookname}}</div>
        </div>
    </div>
</template>

<script>
import bus from './bus'
export default {
    data() {
        return {
            msg: '我是子元素中的大哥',
            num: 0,
            bookname: '《思考快与慢》'
        }
    },
    props: {
        getFatherData: {
          type: Object
        }
    },
    methods: {
        handle: function() {
            bus.$emit('little-event', 2)
        },
        // 要被父组件调用的方法
        setVal: function(val) {
            this.bookname = val
        }
    },
    mounted() {
        bus.$on('big-event', (val) => {
            this.num += val
        })
    }
}

</script>

<style scoped>
.Bigson{
    border: 1px solid #ccc;
    padding: 20px;
}
button{
    margin-left: 15px;
}
</style>
