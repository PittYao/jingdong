<template>
  <div class="warpper">
    <div class="position">
      <span class="iconfont position__icon">&#xe619;</span>
      北京理工大学国防科技园2号楼10层
      <span class="iconfont position__notice">&#xe9cf;</span>
    </div>
    <div class="search">
      <span class="iconfont">&#xe728;</span>
      <span class="search__text">山姆会员商店优惠商品</span>
    </div>
    <div class="banner">
      <img
        class="banner__image"
        src="http://www.dell-lee.com/imgs/vue3/banner.jpg"
      />
    </div>
    <div class="icons">
      <div class="icons__item">
        <img
          class="icons__item__image"
          src="http://www.dell-lee.com/imgs/vue3/超市.png"
        />
        <p class="icons__item__desc">超市便利</p>
      </div>
      <div class="icons__item">
        <img
          class="icons__item__image"
          src="http://www.dell-lee.com/imgs/vue3/菜市场.png"
        />
        <p class="icons__item__desc">菜市场</p>
      </div>
      <div class="icons__item">
        <img
          class="icons__item__image"
          src="http://www.dell-lee.com/imgs/vue3/水果店.png"
        />
        <p class="icons__item__desc">水果店</p>
      </div>
      <div class="icons__item">
        <img
          class="icons__item__image"
          src="http://www.dell-lee.com/imgs/vue3/鲜花.png"
        />
        <p class="icons__item__desc">鲜花绿植</p>
      </div>
      <div class="icons__item">
        <img
          class="icons__item__image"
          src="http://www.dell-lee.com/imgs/vue3/医药健康.png"
        />
        <p class="icons__item__desc">医药健康</p>
      </div>
      <div class="icons__item">
        <img
          class="icons__item__image"
          src="http://www.dell-lee.com/imgs/vue3/家居.png"
        />
        <p class="icons__item__desc">家居时尚</p>
      </div>
      <div class="icons__item">
        <img
          class="icons__item__image"
          src="http://www.dell-lee.com/imgs/vue3/蛋糕.png"
        />
        <p class="icons__item__desc">烘焙蛋糕</p>
      </div>
      <div class="icons__item">
        <img
          class="icons__item__image"
          src="http://www.dell-lee.com/imgs/vue3/签到.png"
        />
        <p class="icons__item__desc">签到</p>
      </div>
      <div class="icons__item">
        <img
          class="icons__item__image"
          src="http://www.dell-lee.com/imgs/vue3/大牌免运.png"
        />
        <p class="icons__item__desc">大牌免运</p>
      </div>
      <div class="icons__item">
        <img
          class="icons__item__image"
          src="http://www.dell-lee.com/imgs/vue3/红包.png"
        />
        <p class="icons__item__desc">红包套餐</p>
      </div>
    </div>
    <div class="gap"></div>
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
  </div>
  <div class="docker">
    <div class="docker__item docker__item--active">
      <div class="iconfont">&#xe61b;</div>
      <div class="docker__title">首页</div>
    </div>
    <div class="docker__item">
      <div class="iconfont">&#xe60a;</div>
      <div class="docker__title">购物车</div>
    </div>
    <div class="docker__item">
      <div class="iconfont">&#xe7e4;</div>
      <div class="docker__title">订单</div>
    </div>
    <div class="docker__item">
      <div class="iconfont">&#xe660;</div>
      <div class="docker__title">我的</div>
    </div>
  </div>
</template>

<style lang="scss">
@import "./style/viriables.scss";
@import "./style/mixins.scss";

.warpper {
  overflow-y: auto;
  position: absolute;
  left: 0;
  top: 0;
  bottom: .5rem;
  right: 0;
  padding: 0 .18rem .01rem .18rem;
}
.position {
  position: relative;
  padding: 0.16rem 0.24rem 0.16rem 0;
  line-height: 0.22rem;
  font-size: 0.16rem;
  @include ellipsis;
  color: $content-fontcolor;
  .position__icon {
    position: relative;
    top: 0.01rem;
    font-size: 0.2rem;
  }
  .position__notice {
    position: absolute;
    right: 0;
    top: 0.17rem;
    font-size: 0.24rem;
  }
}
.search {
  line-height: 0.32rem;
  background: #f5f5f5;
  border-radius: 0.16rem;
  margin-bottom: 0.12rem;
  color: #b7b7b7;
  .iconfont {
    display: inline-block;
    padding: 0 0.08rem 0 0.16rem;
    font-size: 0.16rem;
  }
  &__title {
    font-size: 0.14rem;
    display: inline-block;
  }
}
.banner {
  // padding-bottom防止图片抖动
  height: 0;
  overflow: hidden;
  padding-bottom: 25.4%;
  &__image {
    width: 100%;
  }
}
.icons {
  display: flex;
  flex-wrap: wrap;
  margin-top: 0.16rem;
  &__item {
    width: 20%;
    &__image {
      display: block;
      width: 0.4rem;
      height: 0.4rem;
      margin: 0 auto;
    }
    &__desc {
      text-align: center;
      margin: 0.06rem 0 0.16rem 0;
      color: $content-fontcolor;
    }
  }
}
.gap {
  height: 0.1rem;
  background: $content-bgColor;
  margin: 0 -0.18rem;
}
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
    margin-top: .12rem;
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
      margin-right: .16rem;
    }
    &__highlight {
      color: #e93b3b;
      line-height: 0.18rem;
      font-size: 0.13rem;
    }
  }
}

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
