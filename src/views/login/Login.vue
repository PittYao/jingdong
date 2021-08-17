<template>
  <div class="warpper">
    <img
      class="warpper__img"
      src="http://www.dell-lee.com/imgs/vue3/user.png"
    />
    <div class="warpper__input">
      <input class="warpper__input__content" placeholder="请输入手机号" />
    </div>
    <div class="warpper__input">
      <input class="warpper__input__content" placeholder="请输入密码" />
    </div>
    <div class="warpper__login__button">登陆</div>
    <div class="warpper__login__link">立即注册</div>
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
    width: .66rem;
    height: .66rem;
    margin: 0 auto .4rem auto;
  }
  &__input {
    line-height: .48rem;
    margin: 0 .4rem .16rem .4rem;
    background: #f9f9f9;
    border: 1px solid rgba(0, 0, 0, 0.1);
    border-radius: 6px;
    border-radius: 6px;
    padding: 0 .16rem;
    &__content {
      line-height: .24rem;
      font-size: .16rem;
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
    line-height: .48rem;
    background: #0091ff;
    box-shadow: 0 .04rem .08rem 0 rgba(0, 145, 255, 0.32);
    border-radius: .04rem;
    border-radius: .04rem;
    margin: .32rem .4rem .16rem .4rem;
    text-align: center;
    font-size: .16rem;
    color: #FFF;
  }
  &__login__link {
      text-align: center;
      font-size: .14rem;
      color: $content-notice-fontcolor;
  }
}
</style>

<script>
export default {
  name: 'Login'
}
</script>
