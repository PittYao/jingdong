<template>
  <div class="toast">{{ message }}</div>
</template>

<script>
import { reactive } from 'vue'
export default {
  name: 'Toast',
  props: ['message']
}

// 封装toast
export const useToastEffect = () => {
  // 定义toast
  const toastData = reactive({
    showToast: false,
    toastMsg: ''
  })

  // 定义显示提示框逻辑
  const showToast = (msg) => {
    toastData.showToast = true
    toastData.toastMsg = msg

    // 2秒后取消显示
    setTimeout(() => {
      toastData.showToast = false
      toastData.toastMsg = ''
    }, 2000)
  }

  return { toastData, showToast }
}

</script>

<style lang="scss">
.toast {
  position: fixed;
  left: 50%;
  top: 50%;
  transform: translate(-50%, -50%);
  padding: 0.1rem;
  background: rgba(0, 0, 0, 0.35);
  border-radius: 0.05rem;
  color: #fff;
}
</style>
