<!--
 * @Description: 左侧文件列表组件
 * @Author: sufen
 * @Date: 2020-05-20 16:18:34
 * @LastEditTime: 2020-05-21 10:37:18
 * @LastEditors: sufen
 -->
<template>
  <el-scrollbar class="file-list" wrap-class="scrollbar-filelist" :noresize="false" tag="ul">
    <li v-for="(item, index) in fileList" :key="index" class="file-item">
      <svg t="1592148303818" class="icon" viewBox="0 0 1024 1024" version="1.1" xmlns="http://www.w3.org/2000/svg" p-id="2455" width="25" height="20"><path d="M945.6 824H75.2c-41.6 0-73.6-32-73.6-73.6V272c0-41.6 32-73.6 73.6-73.6h873.6c41.6 0 73.6 32 73.6 73.6v481.6c0 38.4-35.2 70.4-76.8 70.4z m-697.6-145.6v-192l99.2 121.6 99.2-121.6v192h96V345.6h-99.2l-99.2 121.6-99.2-121.6H145.6v334.4l102.4-1.6z m656-166.4h-99.2V345.6h-99.2V512H608l147.2 172.8L904 512z" fill="#888888" p-id="2456"></path></svg>
      <p class="item-title">{{ item.title }}</p>
      <p class="item-time">{{ item.time }}</p>
    </li>
  </el-scrollbar>
</template>

<script>
  export default {
    name: 'FileList',
    props: {
      fileList: {
        type: Array,
        default: () => []
      }
    },
    data() {
      return {}
    }
  }
</script>

<style lang="less" scoped>
  .file-list {
    user-select: none;
    .file-item {
      display: flex;
      align-items: center;
      height: 55px;
      border-bottom: 1px solid #eaeefb;

      .item-icon {
        margin-left: 20px;
        margin-right: 12px;
      }

      .item-title {
        flex: 1;
        margin-right: 5px;
        font-size: 14px;
        text-overflow: ellipsis;
        white-space: nowrap;
        overflow: hidden;
      }
      .item-time {
        width: 80px;
        font-size: 12px;
      }
    }
  }
</style>
<style lang="less">
  .scrollbar-filelist {
    height: calc(100vh - 56px);
    overflow-x: hidden !important;
  }
  .el-scrollbar__bar {
    opacity: 1;

    &.is-vertical {
      right: 0px;
      width: 5px;
      .el-scrollbar__thumb {
        background-color: rgba(144, 147, 153, 0.5);
      }
    }
  }
</style>
