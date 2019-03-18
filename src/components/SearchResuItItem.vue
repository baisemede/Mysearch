<template>
  <div class="search-result-item">
    <a :href="info.url" class="search-result-link">
      <div class="title">{{info.title}}</div>
      <div class="url">{{info.url}}</div>
      <div class="desc">{{info.data}}-{{info.desc}}</div>
    </a>
  </div>
</template>
<script>
export default {
  props: ["info"]
};
</script>
<style lang="less" scoped>
.search-result-item {
  text-align: left;
  padding: 10px;
}
.search-result-link {
  text-decoration: none;
}
.title {
  color: #64abe9;
  font-size: 1.2em;
}
.url {
  color: #006661;
}
.desc {
  color: #545454;
  font-size: 0.8em;
}
</style>
