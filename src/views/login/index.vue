<template>
  <div class="login">
    <!-- 导航栏 -->
    <van-nav-bar title="登录" />
    <!-- 导航栏结束 -->
    <!-- 登录表单 -->
    <van-cell-group>
      <van-field v-model="user.mobile" left-icon="contact" clearable placeholder="请输入手机号" />
      <van-field v-model="user.code" placeholder="请输入验证码" required>
        <van-button round slot="button" size="small" type="primary">发送验证码</van-button>
      </van-field>
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
import request from '@/utils/request'

export default {
  name: 'LoginPage',
  components: {},
  props: {},
  data () {
    return {
      user: {
        mobile: '', // 手机号
        code: '' // 验证码
      }
    }
  },
  computed: {},
  watch: {},
  created () {},
  methods: {
    async onLogin () {
      // 1.获取表单数据
      const user = this.user

      // 2.表单验证

      // 3.请求登录
      const res = await request({
        method: 'POST',
        url: '/app/v1_0/authorizations',
        data: user // 请求体参数
      })
      console.log(res)
      // 4.根据后端返回结果执行处理
    }
  }
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
