<template>
  <div class="position">
    <span class="iconfont position__icon">&#xe619;</span>
    北京理工大学国防科技园2号楼10层
    <span class="iconfont position__notice">&#xe9cf;</span>
  </div>
  <div class="search">
    <span class="iconfont">&#xe728;</span>
    <input class="search__title" placeholder="山姆会员商店优惠商品"/>
  </div>
  <div class="banner">
    <img
      class="banner__image"
      src="http://www.dell-lee.com/imgs/vue3/banner.jpg"
    />
  </div>
  <div class="icons">
    <div class="icons__item" v-for="(item,index) in iconList" :key="index">
      <img
        class="icons__item__image"
        :src="item.imgUrl"
      />
      <p class="icons__item__desc">{{item.desc}}</p>
    </div>
  </div>
  <div class="gap"></div>
</template>

<style lang="scss" scoped>
@import '../../style/viriables.scss';
@import '../../style/mixins.scss';

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
    border: none;
    background: #f5f5f5;
    outline: none;
    width: 80%;
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
</style>

<script>
export default {
  name: 'StaticPart',
  setup (props) {
    const iconList = [
      {
        imgUrl: 'http://www.dell-lee.com/imgs/vue3/超市.png',
        desc: '超市便利'
      },
      {
        imgUrl: 'http://www.dell-lee.com/imgs/vue3/菜市场.png',
        desc: '菜市场'
      },
      {
        imgUrl: 'http://www.dell-lee.com/imgs/vue3/水果店.png',
        desc: '水果店'
      },
      {
        imgUrl: 'http://www.dell-lee.com/imgs/vue3/鲜花.png',
        desc: '鲜花绿植'
      },
      {
        imgUrl: 'http://www.dell-lee.com/imgs/vue3/医药健康.png',
        desc: '医药健康'
      },
      {
        imgUrl: 'http://www.dell-lee.com/imgs/vue3/家居.png',
        desc: '家居时尚'
      },
      {
        imgUrl: 'http://www.dell-lee.com/imgs/vue3/蛋糕.png',
        desc: '烘焙蛋糕'
      },
      {
        imgUrl: 'http://www.dell-lee.com/imgs/vue3/签到.png',
        desc: '签到'
      },
      {
        imgUrl: 'http://www.dell-lee.com/imgs/vue3/大牌免运.png',
        desc: '大牌免运'
      },
      {
        imgUrl: 'http://www.dell-lee.com/imgs/vue3/红包.png',
        desc: '红包套餐'
      }
    ]

    return { iconList }
  }
}
</script>
