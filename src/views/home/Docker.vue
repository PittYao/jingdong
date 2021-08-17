<template>
  <div class="docker">
    <div
      v-for="(item, index) in dockerItemList"
      :class="{ docker__item: true, 'docker__item--active': index === 0 }"
      :key="index"
    >
      <div class="iconfont" v-html="item.iconfont"/>
      <div class="docker__title">{{ item.docker__title }}</div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Docker',
  setup (props) {
    const dockerItemList = [
      {
        iconfont: '&#xe61b;',
        docker__title: '首页'
      },
      {
        iconfont: '&#xe60a;',
        docker__title: '购物车'
      },
      {
        iconfont: '&#xe7e4;',
        docker__title: '订单'
      },
      {
        iconfont: '&#xe660;',
        docker__title: '我的'
      }
    ]

    return { dockerItemList }
  }
}
</script>

<style lang="scss">
@import '../../style/viriables.scss';

.docker {
  display: flex;
  box-sizing: border-box;
  position: absolute;
  bottom: 0;
  left: 0;
  width: 100%;
  height: 0.49rem;
  font-size: 0.14rem;
  padding: 0 0.12rem;
  border-top: 1px solid $content-bgColor;
  color: $content-fontcolor;
  &__item {
    flex: 1;
    text-align: center;
    .iconfont {
      margin: 0.07rem 0 0.02rem 0;
      font-size: 0.18rem;
    }
    &--active {
      color: #1fa4fc;
    }
  }
  &__title {
    // 让浏览器显示小于12px的字符
    font-size: 0.2rem;
    transform: scale(0.5, 0.5);
    transform-origin: center top;
  }
}
</style>
