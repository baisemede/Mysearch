<template>
  <div class="search-pape">
    <search-result-tool-bar :search="search"></search-result-tool-bar>
    <div v-for="(item,index) in searchinfo" :key="index">
      <search-resu-it-item :info="item"></search-resu-it-item>
    </div>
  </div>
</template>
<script>
import SearchResultToolBar from "@/components/SearchResultToolBar";
import SearchResuItItem from "@/components/SearchResuItItem";

export default {
  data() {
    return {
      searchinfo: []
    };
  },
  components: {
    "search-result-tool-bar": SearchResultToolBar,
    "search-resu-it-item": SearchResuItItem
  },
  computed: {
    search() {
      let info = this.$route.params.searchText;
      return info;
    }
  },
  created() {
    this.$nextTick(() => {
      this.getdata();
    });
  },
  beforeRouteUpdate(to, from, next) {
    next();
    this.getdata();
  },
  methods: {
    getdata() {
      this.$ajax
        .get(
          "https://easy-mock.com/mock/5c8f3b23c3ee14532e603191/search/getfarker"
        )
        .then(response => {
          this.searchinfo = response.data[this.search];
          console.log(this.searchinfo);
        })
        .catch(function(error) {
          console.log(error);
        });
    }
  }
};
</script>
