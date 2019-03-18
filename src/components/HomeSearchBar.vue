<template>
  <div class="home-search-bar">
    <input type="text" class="input-search" v-model="searchText" @keydown.enter="dosearch">
    <button class="btn-search" @click="dosearch">搜索一下</button>
  </div>
</template>
<script>
import Util from "@/common/Util";
export default {
  name: "home-search-bar",
  data() {
    return {
      searchText: ""
    };
  },
  methods: {
    dosearch() {
      Util.searchAPI(this.$router, this.searchText);
    }
  }
};
</script>
<style lang="less" scoped>
@import "../themes/base.less";
.home-search-bar {
  max-width: 650px;
}
.input-search {
  outline: none;
  width: 70%;
  height: @home-search-bar-height;
  box-sizing: border-box;
  border: 1px solid @color-border-gray;
  vertical-align: bottom;
  font-size: 1.2em;
  border-top-left-radius: @home-search-bar-border-radius;
  border-bottom-left-radius: @home-search-bar-border-radius;
  padding: 20px;
}
.btn-search {
  background: #3385ff;
  border-bottom: 1px solid #2d78f4;
  outline: none;
  width: 30%;
  height: @home-search-bar-height;
  box-sizing: border-box;
  color: white;
  font-size: 1.6em;
  border: none;
  cursor: pointer;
  border-top-right-radius: @home-search-bar-border-radius;
  border-bottom-right-radius: @home-search-bar-border-radius;
}
</style>

