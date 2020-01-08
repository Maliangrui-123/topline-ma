<template>
  <div class="login">
    <!-- 导航栏 -->
    <van-nav-bar title="登录" />
    <!-- 导航栏结束 -->
    <!-- 登录表单 -->
    <van-cell-group>
      <van-field v-model="user.mobile" required clearable label="手机号" placeholder="请输入手机号" />
      <van-field v-model="user.code" type="password" label="验证码" placeholder="请输入验证码" />
    </van-cell-group>
    <!-- 登录表单结束 -->
    <!-- 登录按钮 -->
    <div class="login-btn">
      <van-button type="info" class="login-box" @click="onLogin">点击登录</van-button>
    </div>
    <!-- 登录按钮结束 -->
  </div>
</template>

<script>
export default {
  name: 'LoginPage',
  components: {},
  props: {},
  data () {
    return {
      user: {
        mobile: '',
        code: ''
      }
    }
  },
  computed: {},
  watch: {},
  created () {},
  methods: {}
}
</script>

<style lang="less" scoped>
  .login-btn{
    padding: 20px;
    .login-box{
      width: 100%;
    }
  }
</style>
