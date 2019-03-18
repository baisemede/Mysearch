<template>
  <div class="home">
    <div class="home-search-panel">
      <mysearch-logo class="my-search-logo"></mysearch-logo>
      <homesearch-bar class="home-search-bar"></homesearch-bar>
    </div>
  </div>
</template>

<script>
import MysearchLogo from "@/components/MysearchLogo";
import HomeSearchBar from "@/components/HomeSearchBar";

export default {
  name: "home",
  components: {
    "mysearch-logo": MysearchLogo,
    "homesearch-bar": HomeSearchBar
  }
};
</script>
<style lang="less" scoped>
.my-search-logo {
  margin-top: 10%;
  margin-bottom: 3%;
}
.home-search-panel {
}
.home-search-bar {
  margin: auto;
}
</style>
