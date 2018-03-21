<template>
  <div id="app">

    <Search :searchKey="page.key" :searchcontent="searchcontent" v-on:increment="go"></Search>

  </div>
</template>

<script>
import Search from './components/search'
import Vue from 'vue'

Vue.use(Search);

export default {
  name: 'app',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      page: {
        // pageNo: Number(this.$route.params.id),
        // pageSize: Number(this.$route.params.pageSize),
        key: ""
      },
      searchcontent:'请输入...', //搜索文本内容
    }
  },
  methods: {
    go: function(payload) {
      this.page.key = payload.key;
      console.log('this.page.key=',this.page.key);
      //这里写你的业务逻辑
    },
  },
  components: {
    Search
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
