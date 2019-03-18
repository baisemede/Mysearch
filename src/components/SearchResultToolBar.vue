<template>
  <div class="search-result-toolbar">
      <img class="logo" src="./../assets/mysearch_logo_small.png" @click="goHome">
    <roundsearch-bar :search='search'></roundsearch-bar>
  </div>
</template>
<script>
import RoundSearchBar from "@/components/RoundSearchBar";
export default {
    name:"search-result-toolbar",
    props: ['search'],
  components: {
    'roundsearch-bar':RoundSearchBar
  },
  methods: {
      goHome(){
          this.$router.push('/')
      }
  }
}
</script>
<style lang="less" scoped>
@import "../themes/base.less";
.search-result-toolbar{
    text-align: left;
    padding: 20px;
    border-bottom: 1px solid @color-border-gray;
}
.logo{
    height: @round-search-bar-height;
    vertical-align: middle;
    margin-right:20px; 
}
</style>
