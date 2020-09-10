<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'Home',
  components: {
    HelloWorld
  },
  directives: {
    demo: {
      // 只调用一次，指令第一次绑定到元素时调用
      // 在这里可以进行一次性的初始化设置 el.parentNode -> null
      bind: (el, binding, vnode) => {},

      // 被绑定元素插入父节点时调用   el.parentNode 访问当前节点的父节点
      // 仅保证父节点存在，但不一定已插入到文档中!!!
      inserted: (el, binding, vnode) => {},

      // 所在组件的VNode 更新时调用
      // 但是可能发生在其子VNode更新之前
      // 指令的值可能发生了改变，也可能没有
      // 但是可以通过比较更新前后的值来忽略不必要的模板更新
      update: (el, binding, vnode, oldVnode) => {},

      // 指令所在在组件的VNode 及其子VNode 全部更新后调用
      // eslint-disable-next-line no-unused-vars
      componentUpdated: (el, binding, vnode, oldVnode) => {},

      // 只调用一次，指令与元素解绑时调用
      unbind: (el, binding, vnode) => {}
    }
    /*function(
      // 指令绑定的元素，可以用来直接操作DOM
      el,
      {
        //指令名，不包括v- 前缀
        name,
        // 指令绑定的值，例如：v-my-directive="1+1"中，
        // 绑定值为2
        value,
        // 指令绑定的前一个值，
        // 仅在update和componentUpdate 钩子中可用
        oldValue,
        // 字符串形式的指令表达式
        //例如 v-my-directive="1+1"中， 表达式为 1+1
        expression,
        // 传递指令的参数，可选
        //例如 v-my-directive:foo中，参数为"foo"
        arg,
        //一个包含修饰符的对象，例如 v-my-directive.foo.bar 中修饰符对象为{foo: true, bar: true}
        modifiers,
      },
      // Vue编译生成的虚拟节点
      vnode,
      // 上一个虚拟节点，仅在update 和 componentUpdated钩子中使用
      oldVnode
    )*/
  }
}
</script>
