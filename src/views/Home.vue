<template>
  <div id="home">
    <div class="header">
      <!-- @click="$router.push('/address')"是点击定位的地址跳转到address页面 -->
      <!-- 从Home.vue向Address.vue传递city数据 -->
      <div class="address_map" @click="$router.push({name: 'address',params: {city: city}})">
        <i class="iconfont icondingwei"></i>
        <span>{{address}}</span>
        <i class="iconfont iconshouhuodizhi"></i>
      </div>
      <div class="shop_search">
        <i class="iconfont iconsousuo"></i>
        搜索商家 商家名称
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "home",
  computed: {
    address() {
      return this.$store.getters.address;
    },
    city() {
      return (
        this.$store.getters.location.addressComponent.city ||
        this.$store.getters.location.addressComponent.province
      );
    }
  }
};
</script>
<style scoped>
.home {
  width: 100%;
  height: 100%;
  overflow: auto;
  box-sizing: border-box;
}
.header {
  background-color: #009eef;
  padding: 16px;
}
.header .address_map {
  color: #fff;
  font-weight: bold;
}
.address_map i {
  margin: 0 3px;
  font-size: 18px;
}
.address_map span {
  display: inline-block;
  width: 80%;
  overflow: hidden;
  white-space: nowrap;
  text-overflow: ellipsis;
}
.header .shop_search {
  margin-top: 10px;
  background-color: #fff;
  padding: 10px 0;
  border-radius: 4px;
  text-align: center;
  color: #aaa;
}
</style>
