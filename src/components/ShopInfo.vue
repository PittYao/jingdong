<template>
  <div class="shop">
    <img class="shop__img" :src="item.imgUrl" />
    <div
      :class="{'shop__content':true,'shop__content--bodered':hideBorder ? false : true}"
    >
      <div class="shop__content__title">{{ item.name }}</div>
      <div class="shop__content__tags">
        <sapn class="shop__content__tag">月售{{ item.sales }}</sapn>
        <sapn class="shop__content__tag">起送{{ item.expressLimit }}</sapn>
        <sapn class="shop__content__tag">基础运费{{ item.expressPrice }}</sapn>
      </div>
      <p class="shop__content__highlight">
        {{ item.slogan }}
      </p>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ShopInfo',
  props: ['item', 'hideBorder']
}
</script>

<style lang="scss">
@import '../style/viriables.scss';

.shop {
  display: flex;
  margin-top: .12rem;
  &__img {
    width: .56rem;
    height: .56rem;
    margin: 0 .16rem 0 0;
  }
  &__content {
    flex: 1;
    width: 100%;
    &--bodered {
      border-bottom: 1px solid $content-bgColor;
    }
    &__title {
      font-size: .16rem;
      line-height: .22rem;
      color: $content-fontcolor;
    }
    &__tags {
      margin: .08rem 0;
      line-height: .18rem;
      font-size: .13rem;
      color: $content-fontcolor;
    }
    &__tag {
      margin-right: .16rem;
    }
    &__highlight {
      color: #e93b3b;
      line-height: .18rem;
      font-size: .13rem;
    }
  }
}
</style>
