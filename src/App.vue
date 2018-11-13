<template>
  <div id="app">
    <!-- 我路由的内容被加载过一次之后，将其放在内存中，下一次再进入此路由，不需要再重新加载 将内存的取出来用就可以 -->
    <keep-alive>
      <!-- 显示当前路由所对应的组件 -->
      <router-view/>
    </keep-alive>
  </div>
</template>

<script>
export default {
  name: 'App'
}
</script>

<style>

</style>
