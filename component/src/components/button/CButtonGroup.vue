<template>
    <div class="button-group">
        <slot name="default"></slot>
    </div>
</template>

<script>
    export default {
        name: "CButtonGroup"
    }
</script>

<style lang="scss" scoped>
    .button-group {
        button:first-child {
            border-top-right-radius: 0;
            border-bottom-right-radius: 0;
        }
        button:last-child {
            border-top-left-radius: 0;
            border-bottom-left-radius: 0;
        }
        /*
            TODO 理解CSS优先级
            当 group 中间的按钮被设置为 round || circle 的时候，不会四角变。
            可能是优先级的原因。
        */
        button:not(:first-child):not(:last-child) {
            border-radius: 0;
        }
    }
</style>