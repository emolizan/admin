<template>
  <div class="center">
    <el-form class="formtop" ref="form" :model="form" label-width="80px">
      <el-form-item class="user" label="用户名">
        <el-input ></el-input>
      </el-form-item>
      <el-form-item class="user" label="密码">
        <el-input type="password" ></el-input>
      </el-form-item>
      <el-form-item class="user">
        <el-button type="primary" @click="login">登录</el-button>
      </el-form-item>
    </el-form>
  </div>
</template>

<script>
export default {
  name: 'login',
  data () {
    return {
    }
  },
  methods: {
    login(){
      alert('登录成功');
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.center{
  padding-top: 50px;
  width: 600px;
  height: 300px;
  border-radius: 10px;
  position: absolute;
  top:40%;
  left: 50%;
  transform: translate(-50%, -50%);
  border: 2px solid rgb(238, 238, 238);
  box-shadow: 0px 0px 10px #dbdbdb;
}
.user{
  margin-top: 30px;
  width: 300px;
  margin-left: 110px;
}
</style>