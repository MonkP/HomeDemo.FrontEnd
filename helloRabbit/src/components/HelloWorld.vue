<template>
  <div class="">这是兔兔的页面</div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.dice{
  width: 99px;
  height: 99px;
  border: 1px solid #AAAAAA;
  border-radius: 9px;
  display:flex;
  flex-direction: column;
  justify-content: space-between;
}
.row{
  width:100%;
  height:100%;
  display:flex;
  justify-content: space-between;
  align-items: center;
}
.points{
  width: 14px;
  height:14px;
  background-color:black;
  border-radius: 7px;
}
</style>
