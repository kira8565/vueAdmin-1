<template>
    <el-form :model="form" :rules="rules2" ref="form" label-position="left" label-width="0px"
             class="demo-ruleForm card-box loginform">
        <h3 class="title">系统登录</h3>
        <el-form-item prop="account">
            <el-input type="text" v-model="form.account" auto-complete="off" placeholder="用户名"></el-input>
        </el-form-item>
        <el-form-item prop="checkPass">
            <el-input type="password" v-model="form.checkPass" auto-complete="off" placeholder="密码"></el-input>
        </el-form-item>
        <el-checkbox v-model="checked" checked style="margin:0px 0px 35px 0px;">记住密码</el-checkbox>
        <el-form-item style="width:100%;">
            <el-button type="primary" style="width:100%;" @click.native.prevent="loginAction">登录</el-button>
        </el-form-item>
    </el-form>
</template>

<script>
  export default {
    data() {
      return {
        form: {
          account: '',
          checkPass: ''
        },
        rules2: {
          account: [
            { required: true, message: '请输入账号', trigger: 'blur' },
          ],
          checkPass: [
            { required: true, message: '请输入密码', trigger: 'blur' },
          ]
        },
        checked: true
      };
    },
    methods: {
      handleReset2() {
        this.$refs.form.resetFields();
      },
      loginAction(ev) {
        var _this=this;
        this.$refs.form.validate((valid) => {
          if (valid) {
            _this.$router.replace('/table');
          } else {
            return false;
          }
        });
      }
    }
  }
















</script>

<style scoped>
  .card-box {
    padding: 20px;
    /*box-shadow: 0 0px 8px 0 rgba(0, 0, 0, 0.06), 0 1px 0px 0 rgba(0, 0, 0, 0.02);*/
    -webkit-border-radius: 5px;
    border-radius: 5px;
    -moz-border-radius: 5px;
    background-clip: padding-box;
    margin-bottom: 20px;
    background-color: #F9FAFC;
    margin: 120px auto;
    width: 400px;
    border: 2px solid #8492A6;
  }
  
  .title {
    margin: 0px auto 40px auto;
    text-align: center;
    color: #505458;
  }
  
  .loginform {
    width: 350px;
    padding: 35px 35px 15px 35px;
  }
















</style>