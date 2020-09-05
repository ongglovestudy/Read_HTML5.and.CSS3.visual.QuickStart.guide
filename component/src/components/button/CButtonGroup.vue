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
        /*
          TODO 对于icon的处理
          有两种方式：
            一种是直接引入svg文件
                操作比较简单，只需要将svg标签加入template中就可以了
                https://ant.design/components/icon-cn/#自定义-Icon
                https://github.com/ant-design/ant-design/issues/10353

            一种是将文件转换成为字体文件，然后通过CSS引入到页面中
                需要将图标制作成位字体格式文件，每个图标对应上不同的编码，
                使用的使用在CSS类中的 content 属性调用。
                https://github.com/ant-design/antd-init/tree/master/examples/local-iconfont


            图标对比的例子
                https://zhuanlan.zhihu.com/p/199778814
         */
        button:not(:first-child):not(:last-child) {
            border-radius: 0;
        }
    }
</style>