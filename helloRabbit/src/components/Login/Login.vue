<template>
  <el-container>
    <el-header>
      <h1>不知道干嘛好的登录页</h1>
    </el-header>
    <el-main>
      <div class="login-form">
        <el-form :model="login">
          <el-form-item label>
            <el-input v-model="login.userName" placeholder="请输入用户名"></el-input>
          </el-form-item>
          <el-form-item label>
          <el-input v-model="login.pwd" placeholder="请输入登录密码" show-password></el-input>
          </el-form-item>
          <el-form-item label>
          <el-checkbox v-model="remember">记住密码</el-checkbox>
          </el-form-item>
          <el-form-item label>
          <el-button @click="doLogin" class="btn-login" type="primary" round :loading="loading">登录</el-button>
          </el-form-item>
        </el-form>
      </div>
    </el-main>
    <el-footer>
      <el-button @click="goDices" type="text">乖乖点这里</el-button>
    </el-footer>
  </el-container>
</template>
<script>
import { Message, Loading } from "element-ui";
import { debug } from 'util';

export default {
  name: "Login",
  data() {
    return {
      login: {
        userName: "",
        pwd: ""
      },
      remember: false,
      loading: false
    };
  },
  methods: {
    //TODO 假登录
    doLogin() {
      console.log(this.login.userName + ' ' + this.login.pwd)
    },
    goDices() {
      this.$router.push({ path: "/timing" });
    }
  }
};
</script>
<style scoped>
.login-form {
  width: 80%;
  margin: 0 10%;
}
.btn-login {
  width: 100%;
}
</style>
