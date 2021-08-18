<template>
  <div class="warpper">
    <img
      class="warpper__img"
      src="http://www.dell-lee.com/imgs/vue3/user.png"
    />
    <div class="warpper__input">
      <input
        class="warpper__input__content"
        placeholder="请输入手机号"
        v-model="username"
      />
    </div>
    <div class="warpper__input">
      <input
        class="warpper__input__content"
        placeholder="请输入密码"
        type="password"
        v-model="password"
      />
    </div>
    <div class="warpper__login__button" @click="handleLogin">登陆</div>
    <div class="warpper__login__link" @click="handleRegister">立即注册</div>
    <Toast v-if="show" :message="toastMsg" />
  </div>
</template>

<style lang="scss" scoped>
@import '../../style/viriables.scss';

.warpper {
  // 垂直居中
  position: absolute;
  left: 0;
  right: 0;
  top: 50%;
  transform: translateY(-50%);
  &__img {
    display: block;
    width: 0.66rem;
    height: 0.66rem;
    margin: 0 auto 0.4rem auto;
  }
  &__input {
    line-height: 0.48rem;
    margin: 0 0.4rem 0.16rem 0.4rem;
    background: #f9f9f9;
    border: 1px solid rgba(0, 0, 0, 0.1);
    border-radius: 6px;
    border-radius: 6px;
    padding: 0 0.16rem;
    &__content {
      line-height: 0.24rem;
      font-size: 0.16rem;
      border: none;
      background: none;
      outline: none;
      width: 100%;
      color: $content-notice-fontcolor;
      &::placeholder {
        color: $content-notice-fontcolor;
      }
    }
  }
  &__login__button {
    line-height: 0.48rem;
    background: #0091ff;
    box-shadow: 0 0.04rem 0.08rem 0 rgba(0, 145, 255, 0.32);
    border-radius: 0.04rem;
    border-radius: 0.04rem;
    margin: 0.32rem 0.4rem 0.16rem 0.4rem;
    text-align: center;
    font-size: 0.16rem;
    color: #fff;
  }
  &__login__link {
    text-align: center;
    font-size: 0.14rem;
    color: $content-notice-fontcolor;
  }
}
</style>

<script>
import { useRouter } from 'vue-router'
import { post } from '../../utils/request'
import { reactive, toRefs } from 'vue'
import Toast, { useToastEffect } from '../../components/Toast.vue'

// 登录逻辑
const useLoginEffect = (showToast) => {
  const route = useRouter()

  // 定义model
  const data = reactive({
    username: '',
    password: ''
  })

  const handleLogin = async () => {
    try {
      const result = await post('11/api/auth/login', data)
      console.log(result)
      // 认证成功
      if (result?.error === 0) {
        localStorage.isLogin = true
        // 操作路由跳转到首页
        route.push({ name: 'Home' })
      } else {
        showToast('登录失败')
      }
    } catch (error) {
      showToast('请求失败')
    }
  }

  // 解构
  const { username, password } = toRefs(data)

  return { username, password, handleLogin }
}

// 注册跳转
const useRegisterEffect = () => {
  const route = useRouter()

  const handleRegister = () => {
    route.push({ name: 'Register' })
  }

  return { handleRegister }
}

export default {
  name: 'Login',
  components: { Toast },
  // setup 只控制流程
  setup (props) {
    // 引入弹窗
    const { show, toastMsg, showToast } = useToastEffect()
    // 引入登录逻辑
    const { username, password, handleLogin } = useLoginEffect(showToast)
    // 引入注册逻辑
    const { handleRegister } = useRegisterEffect()

    return {
      handleLogin,
      handleRegister,
      username,
      password,
      show,
      toastMsg,
      showToast
    }
  }
}
</script>
