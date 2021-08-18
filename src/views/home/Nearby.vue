<template>
  <div class="nearby">
    <div class="nearby__title">附近店铺</div>
    <div
      class="nearby__item"
      v-for="item in nearByList"
      :key="item._id"
    >
      <img class="nearby__item__img" :src="item.imgUrl" />
      <div class="nearby__content">
        <div class="nearby__content__title">{{ item.name }}</div>
        <div class="nearby__content__tags">
          <sapn class="nearby__content__tag">月售{{ item.sales }}</sapn>
          <sapn class="nearby__content__tag">起送{{ item.expressLimit }}</sapn>
          <sapn class="nearby__content__tag"
            >基础运费{{ item.expressPrice }}</sapn
          >
        </div>
        <p class="nearby__content__highlight">
          {{ item.slogan }}
        </p>
      </div>
    </div>
  </div>
</template>

<script>
import { ref } from '@vue/reactivity'
import { get } from '../../utils/request'

const useNearByListEffect = () => {
  const nearByList = ref([])

  const getNearByList = async () => {
    const result = await get('/shop/hot-list')

    if (result?.errno === 0 && result?.data?.length) {
      nearByList.value = result.data
    }
  }

  return { getNearByList, nearByList }
}
export default {
  name: 'Nearby',
  setup (props) {
    const { getNearByList, nearByList } = useNearByListEffect()
    getNearByList()

    return { nearByList }
  }
}
</script>

<style lang="scss" scoped>
@import '../../style/viriables.scss';

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
