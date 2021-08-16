<template>
  <div class="nearby">
    <div class="nearby__title">附近店铺</div>
    <div class="nearby__item">
      <img
        class="nearby__item__img"
        src="http://www.dell-lee.com/imgs/vue3/near.png"
      />
      <div class="nearby__content">
        <div class="nearby__content__title">沃尔玛</div>
        <div class="nearby__content__tags">
          <sapn class="nearby__content__tag">月售1万+</sapn>
          <sapn class="nearby__content__tag">起送¥0</sapn>
          <sapn class="nearby__content__tag">基础运费¥5</sapn>
        </div>
        <p class="nearby__content__highlight">
          VIP尊享满89元减4元运费券（每月3张）
        </p>
      </div>
    </div>
    <div class="nearby__item">
      <img
        class="nearby__item__img"
        src="http://www.dell-lee.com/imgs/vue3/near.png"
      />
      <div class="nearby__content">
        <div class="nearby__content__title">沃尔玛</div>
        <div class="nearby__content__tags">
          <sapn class="nearby__content__tag">月售1万+</sapn>
          <sapn class="nearby__content__tag">起送¥0</sapn>
          <sapn class="nearby__content__tag">基础运费¥5</sapn>
        </div>
        <p class="nearby__content__highlight">
          VIP尊享满89元减4元运费券（每月3张）
        </p>
      </div>
    </div>
    <div class="nearby__item">
      <img
        class="nearby__item__img"
        src="http://www.dell-lee.com/imgs/vue3/near.png"
      />
      <div class="nearby__content">
        <div class="nearby__content__title">沃尔玛</div>
        <div class="nearby__content__tags">
          <sapn class="nearby__content__tag">月售1万+</sapn>
          <sapn class="nearby__content__tag">起送¥0</sapn>
          <sapn class="nearby__content__tag">基础运费¥5</sapn>
        </div>
        <p class="nearby__content__highlight">
          VIP尊享满89元减4元运费券（每月3张）
        </p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Nearby'
}
</script>

<style lang="scss">
@import "../../style/viriables.scss";

.nearby {
  &__title {
    font-size: 0.18rem;
    font-weight: normal;
    line-height: 0.25rem;
    color: $content-fontcolor;
    margin: 0.16rem 0 0.02rem 0;
  }
  &__item {
    display: flex;
    margin-top: 0.12rem;
    &__img {
      width: 0.56rem;
      height: 0.56rem;
      margin: 0 0.16rem 0 0;
    }
  }
  &__content {
    width: 100%;
    border-bottom: 1px solid $content-bgColor;
    &__title {
      font-size: 0.16rem;
      line-height: 0.22rem;
      color: $content-fontcolor;
    }
    &__tags {
      margin: 0.08rem 0;
      line-height: 0.18rem;
      font-size: 0.13rem;
      color: $content-fontcolor;
    }
    &__tag {
      margin-right: 0.16rem;
    }
    &__highlight {
      color: #e93b3b;
      line-height: 0.18rem;
      font-size: 0.13rem;
    }
  }
}
</style>
