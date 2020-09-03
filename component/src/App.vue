<template>
  <c-button size="small" type="danger" round></c-button>
  <e-button size="small" type="danger" disabled round>提交</e-button>
</template>

<script>
import CButton from './components/button/CButton.vue'
import EButton from "./components/button/EButton.vue";

export default {
  name: 'App',
  components: {
    EButton,
    CButton
  }
}
</script>
