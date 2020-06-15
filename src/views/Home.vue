<template>
  <div class="home">
    <div class="sidebar-container">
      <file-search v-model="searchTitle"></file-search>
      <file-list :fileList="fileList"></file-list>
    </div>
    <div class="main-container">
      <file-edit
          v-model="fileItem.content"
          :title.sync="fileItem.title"
          :boxShadow="false"
          :subfield="false"
          :shortCut="false"
          @change="onSubmit"
      ></file-edit>
    </div>
  </div>
</template>

<script>
import fileSearch from '../components/fileSearch'
import fileList from '../components/fileList'
import FileEdit from "../components/fileEdit";

export default {
  name: 'Home',
  components: {
    FileEdit,
    fileSearch,
    fileList
  },
  data () {
    return {
      searchTitle: '',
      fileList: [
        {id: 1, title: '文件名 1', time: '2020-06-21'},
        {id: 2, title: '文件名 2', time: '2020-06-21'},
        {id: 3, title: '文件名 3', time: '2020-06-21'},
        {id: 4, title: '文件名 4', time: '2020-06-21'},
        {id: 5, title: '文件名 5', time: '2020-06-21'},
        {id: 6, title: '文件名 6', time: '2020-06-21'},
        {id: 7, title: '文件名 1', time: '2020-06-21'},
        {id: 8, title: '文件名 2', time: '2020-06-21'},
        {id: 9, title: '文件名 3', time: '2020-06-21'},
        {id: 10, title: '文件名 4', time: '2020-06-21'},
        {id: 11, title: '文件名 5', time: '2020-06-21'},
        {id: 12, title: '文件名 6', time: '2020-06-21'},
        {id: 13, title: '文件名 6', time: '2020-06-21'},
        {id: 14, title: '文件名 6', time: '2020-06-21'},
        {id: 15, title: '文件名 6', time: '2020-06-21'},
        {id: 16, title: '文件名 6', time: '2020-06-21'},
        {id: 17, title: '文件名 6', time: '2020-06-21'},
        {id: 18, title: '文件名 6', time: '2020-06-21'},
      ],
      fileItem: {
        content: 'aaa',
        title: 'bbb'
      }
    }
  },
  methods: {
    onSubmit: function (e) {
      console.log(e)
    }
  }
}
</script>
<style lang="less" scoped>
  .home{
    display: flex;
    .sidebar-container{
      width: 300px;
      height: 100vh;
      border-right: 1px solid #eaeefb;
    }
    .main-container{
      flex: 1;
    }
  }
</style>
