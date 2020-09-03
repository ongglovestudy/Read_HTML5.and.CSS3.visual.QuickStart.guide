<template>
  <button
    :disabled="disable ? 'disabled':''"
    :class="[
      type,
      size,
      {
        round: round,
      }
    ]"
  >
    <span v-if="$slots.default"><slot></slot></span>
    <span v-else>提交</span>
  </button>
</template>

<script>
export default {
  name: 'CButton',
  props: {
    type: {
      type: String,
      default: 'default'
    },
    size: {
      type: String,
      default: 'normal'
    },
    round: Boolean,
    disable: Boolean,
  },
  data() {
    return {

    }
  },
  computed: {

  }
}
</script>

<style lang="scss" scoped>

  $button-type-color: (
    'danger': #e50b0b,
    'default': #38bee7,
  );

  @mixin type($type) {
    $color: map_get($button-type-color, $type);
    background: rgba($color, 0.6);
    border: none;
    // color: $color;

    &:hover {
      background: rgba($color, 0.8);
      // color: rgb($color, 1);
    }

    &:active {
      background: rgba($color, 1);
    }

    &:disabled {
      background: rgba($color, .1);
      cursor: not-allowed;
    }
  }

  button {

    // 点选时候不出现现在边框
    outline: none;
    // 字体粗细
    font-weight: 300;

    // 按钮主题
    &.default {
      border-radius: 4px;
      @include type('default')
    }
    &.danger {
      border-radius: 4px;
      @include type('danger')
    }

    // 按钮圆角
    &.round {
      border-radius: 20px;
    }

    // 按钮尺寸
    &.mini {
      padding: .4rem 1rem;
      font-size: .6rem;
    }
    &.small {
      padding: .5rem 1rem ;
      font-size: .8rem;
    }
    &.normal {
      padding: .6rem 1rem;
      font-size: 1rem;
    }
    &.large {
      padding: .7rem 1rem;
      font-size: 1.2rem;
    }
  }

</style>