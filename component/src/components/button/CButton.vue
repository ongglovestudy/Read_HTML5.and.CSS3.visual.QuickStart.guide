<template>
  <button
    :disabled="buttonDisable"
    :class="[
      type,
      size,
      {
        circle: circle,
        round: round,
      }
    ]"
  >
    <slot name="default">提交</slot>
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
    circle: Boolean,
    disabled: Boolean,
  },
  data() {
    return {

    }
  },
  computed: {
    buttonDisable() {
      return this.disabled
    }
  }
}
</script>

<style lang="scss" scoped>

  $button-type-color: (
    'danger': #e50b0b,
    'default': #38bee7,
    'text': #ffffff,
  );

  @mixin type($type) {
    $color: map_get($button-type-color, $type);
    color: #FFFFFF;
    @if($type == 'text') {
      color: #409EFF;
      background: none;
    } @else {
      background: rgba($color, 0.6);
    }
    border: none;

    &:hover {
      background: rgba($color, 0.8);
    }

    &:active {
      background: rgba($color, 1);
    }

    &:disabled {
      background: rgba($color, .5);
      cursor: not-allowed;
    }
  }

  button {

    // 点选时候不出现现在边框
    outline: none;
    // 字体粗细
    font-weight: 300;
    cursor: pointer;

    // 按钮主题
    &.default {
      border-radius: 4px;
      @include type('default');
    }
    &.danger {
      border-radius: 4px;
      @include type('danger');
    }
    &.text {
      @include type('text');
    }

    // 按钮圆角
    &.round {
      border-radius: 20px;
    }
    &.circle {
      border-radius: 50%;
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