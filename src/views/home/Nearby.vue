<template>
  <div class="nearby">
    <div class="nearby__title">附近店铺</div>
    <ShopInfo
      v-for="item in nearByList"
      :key="item._id"
      :item="item"
    />
  </div>
</template>

<script>
import { ref } from '@vue/reactivity'
import { get } from '../../utils/request'
import ShopInfo from '../../components/ShopInfo.vue'

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
  components: {
    ShopInfo
  },
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
}
</style>
