<template>
  <button>
    <!-- 后备默认内容 -->
    <slot>提交</slot>
  </button>
</template>

<script>
export default {
  name: 'CButton',
  props: {
    msg: String
  },
  data() {
    return {

    }
  }
}
</script>

<style scoped>
button {
  border-radius: 1rem;
}
</style>