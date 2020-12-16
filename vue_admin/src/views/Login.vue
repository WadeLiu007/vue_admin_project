<template>
  <div class="login_container">
    <div class="login_box">
      <div class="avatar_box">
        <img src="../assets/header.jpg" alt="" />
      </div>
      <el-form
        :model="loginForm"
        label-width="80px"
        ref="loginRef"
        :rule="loginRule"
      >
        <el-form-item label="用户名:" prop="username">
          <el-input v-model="loginForm.username"></el-input>
        </el-form-item>
        <el-form-item label="密码:" prop="password">
          <el-input v-model="loginForm.password"></el-input>
        </el-form-item>
        <el-form-item>
          <el-button type="primary">登录</el-button>
          <el-button>重置</el-button>
        </el-form-item>
      </el-form>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      loginForm: {
        username: "",
        password: "",
      },
      loginRule: {
        username: [
          { require: true, message: "输入框不能为空", trigger: "blur" }
        ],
        password:[
          { require: true, message: "输入框不能为空", trigger: "blur" }
        ]
      },
    };
  },
};
</script>

<style lang="scss" scoped>
.login_container {
  width: 100%;
  height: 100%;
  background: #2b4b6b;
  .login_box {
    width: 450px;
    height: 300px;
    background-color: white;
    position: relative;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    border-radius: 3px;
    .avatar_box {
      width: 130px;
      height: 130px;
      border: 1px solid #eee;
      border-radius: 50%;
      box-shadow: 0 0 10px #ddd;
      padding: 10px;
      position: absolute;
      left: 50%;
      transform: translate(-50%, -50%);
      img {
        width: 100%;
        height: 100%;
        border-radius: 50%;
      }
    }
  }
}
</style>
