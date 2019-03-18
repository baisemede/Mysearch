<template>
  <div class="round-search-bar">
    <input type="text" v-model="searchinfo" class="input-search" @keydown.enter="doSearch">
    <button class="btn-search" @click="doSearch">
      <img src="./../assets/icon_search.svg" class="icon-search">
    </button>
  </div>
</template>
<script>
import Util from "@/common/Util";

export default {
  name: "round-search-bar",
  data() {
    return {
      searchinfo:''
    };
  },
  created () {
    this.searchinfo=this.search
  },
  props: ["search"],
  methods: {
    doSearch() {
      Util.searchAPI(this.$router, this.searchinfo);
    }
  }
};
</script>
<style lang="less" scoped>
@import "../themes/base.less";
.round-search-bar {
  width: 500px;
  position: relative;
  border-radius: 22px;
  background-color: #f1f3f4;
  border: none;
  display: inline-block;
  &:hover {
    background-color: #e8eaed;
  }
}
.input-search {
  width: 100%;
  font-size: 1.2em;
  background: transparent;
  height: @round-search-bar-height;
  border: none;
  padding: 0 8px;
  box-sizing: border-box;
  outline: none;
}
.btn-search {
  height: @round-search-bar-height;
  position: absolute;
  right: 0;
  top: 50%;
  transform: translateY(-50%);
  border: none;
  background: none;
  outline: none;
  cursor: pointer;
}
.icon-search {
  width: 30px;
  height: 30px;
  margin-right: 10px;
}
</style>
