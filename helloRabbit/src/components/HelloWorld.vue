<template>
<body>
  <h1>This is Rabbit's page</h1>
  <div id="time">{{ today }}</div>
  <div>
    今天是兔兔和小乖认识的第
    <span class="days">{{ getDays }}</span>天
  </div>
  <div>
    婚礼倒计时
    <span class="marryDays">{{ getMarryDays }}</span>天
  </div>
  <!-- <button @click="getTime">点我</button> -->
</body>
</template>

<script>
import { setInterval } from 'timers'

export default {
  name: 'HelloWorld',
  data() {
    return {
      today: new Date().toLocaleString()
    }
  },
  computed: {
    getToday: function() {
      let date = new Date()
      return date.toLocaleString()
      //return date.getFullYear()+"年"+(date.getMonth()+1)+"月"+date.getDate()+"日";
    },
    getDays: function() {
      let dayStart = new Date('2011/10/11')
      let today = new Date()
      let days = Math.ceil((today - dayStart) / (24 * 60 * 60 * 1000))
      return days
    },
    getMarryDays: function() {
      let dayStart = new Date('2020/10/06')
      let today = new Date()
      let days = Math.ceil((dayStart - today) / (24 * 60 * 60 * 1000))
      return days
    }
  },
  mounted() {
    //setInterval里的作用域跟外层方法不一样，需要把this保存在外层闭包里
    let self = this;
    setInterval(function() {
      self.today = new Date().toLocaleString()
    }, 1000)
  }
  // methods:{
  //   getTime:function(){
  //     setInterval(function(){
  //       this.today = new Date().toLocaleString();
  //     },1000)
  //   }
  // }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
div {
  margin-top: 10px;
  font-size: 20px;
  font-family: 微软雅黑;
}
.days {
  font-size: 30px;
  color: red;
  font-weight: bold;
}
.marryDays {
  font-size: 30px;
  color: green;
  font-weight: bold;
}
</style>
