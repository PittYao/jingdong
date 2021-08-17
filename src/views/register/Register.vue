<template>
  <div class="warpper">
    <img
      class="warpper__img"
      src="http://www.dell-lee.com/imgs/vue3/user.png"
    />
    <div class="warpper__input">
      <input class="warpper__input__content" placeholder="请输入手机号" v-model="data.username" />
    </div>
    <div class="warpper__input">
      <input
        class="warpper__input__content"
        placeholder="请输入密码"
        type="password"
        v-model="data.password"
      />
    </div>
    <div class="warpper__input">
      <input
        class="warpper__input__content"
        placeholder="确认密码"
        type="password"
      />
    </div>
    <div class="warpper__register__button" @click="handleRegister">注册</div>
    <div class="warpper__register__link" @click="handelLoginClick">
      已有账号去登陆
    </div>
    <Toast v-if="toastData.showToast" :message="toastData.toastMsg"/>
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
  &__register__button {
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
  &__register__link {
    text-align: center;
    font-size: 0.14rem;
    color: $content-notice-fontcolor;
  }
}
</style>

<script>
import { post } from '../../utils/request'
import { useRouter } from 'vue-router'
import Toast, { useToastEffect } from '../../components/Toast.vue'

export default {
  name: 'Register',
  components: { Toast },
  setup (props) {
    // 获取路由
    const route = useRouter()

    // 定义model
    const data = {
      username: '',
      password: ''
    }

    // 引用弹框
    const { toastData, showToast } = useToastEffect()

    const handleRegister = async () => {
      try {
        const result = await post('/api/auth/register', data, {})

        if (result?.error === 0) {
          localStorage.isLogin = true
          // 操作路由跳转
          route.push({ name: 'Home' })
        } else {
          showToast('注册失败')
        }
      } catch (error) {
        showToast('请求失败')
      }
    }

    const handelLoginClick = () => {
      route.push({ name: 'Login' })
    }

    return { handleRegister, handelLoginClick, data, toastData, showToast }
  }
}
</script>
