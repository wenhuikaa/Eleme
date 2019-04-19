<template>
  <div id="index">
    <!-- index下有子路由，所以不要忘记<router-view> -->
    <!-- 路由匹配到的组件将显示到这里 -->
    <router-view></router-view>
    <TabBar :data="tabbarData"/>
  </div>
</template>

<script>
import TabBar from "../components/TabBar";
export default {
  name: "index",
  data() {
    return {
      tabbarData: [
        { title: "首页", icon: "iconshouye", path: "/home" },
        { title: "订单", icon: "icondingdan", path: "/order" },
        { title: "我的", icon: "iconwode", path: "/me" }
      ]
    };
  },
  components: {
    TabBar
  }
};
</script>

<style scoped>
.index {
  width: 100%;
  /* 因为底部导航本来就有45px */
  height: calc(100%-45px);
}
</style>