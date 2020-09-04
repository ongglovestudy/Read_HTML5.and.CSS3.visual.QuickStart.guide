<template>
  <c-button-group>
    <template #default>
      <c-button></c-button>
      <c-button></c-button>
      <c-button round></c-button>
    </template>
  </c-button-group>
  <hr>
  <e-button-group>
    <e-button>提交</e-button>
    <e-button round>提交</e-button>
    <e-button circle>提交</e-button>
  </e-button-group>
</template>

<script>
import CButton from './components/button/CButton.vue'
import EButton from "./components/button/el/EButton.vue";
import EButtonGroup from "./components/button/el/EButtonGroup.vue";
import CButtonGroup from "./components/button/CButtonGroup.vue";

export default {
  name: 'App',
  components: {
    CButtonGroup,
    EButtonGroup,
    EButton,
    CButton
  }
}
</script>
