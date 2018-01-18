<template>
  <div class="hello">
    <input v-model="val"><br/>
    <test :testVal="val" @on-val-change="onResultChange"></test><br/>
    <button class="button" v-on:click="buttonClicked">
      <span>click</span>
    </button>
  </div>
</template>

<script>
  export default {
    name: 'hello',
    data () {
      return {
        val: 1
      }
    },
    methods: {
      buttonClicked: function () {
        console.log(this.val)
      },
      onResultChange (val) {
        this.val = val // ④外层调用组件方注册变更方法，将组件内的数据变更，同步到组件外的数据状态中
      }
    },
    watch: {
      val (val) {
        console.log(val)
      }
    },
    components: {
      'test': {
        props: ['testVal'],
        data: function () {
          return {
            myVal: this.testVal // ①创建props属性testVal的副本--myVal
          }
        },
        template: "<input v-model='myVal'/>",
        watch: {
          testVal (val) {
            this.myVal = val // 新增testVal的watch，监听变更并同步到myVal上
          },
          myVal (val) {
            this.$emit('on-val-change', val) // ③组件内对myVal变更后向外部发送事件通知
          }
        }
      }
    }
  }
</script>
