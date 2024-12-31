<template>
  <!-- <el-card class="update"> -->
  <!-- <template #header> -->
  <!-- <div class="card-header"> -->
  <div class="title">
    <div class="i-icon" style="margin-top: 40px">
      <tool theme="outline" size="22" fill="#fff" />
      <span>更新日志</span>
    </div>
  </div>
  <!-- <span>更新日志</span> -->
  <!-- </div> -->
  <!-- </template> -->
  <el-card class="update">
    <div class="upnote">
      <div v-for="item in upData.new" :key="item.key" class="uptext">
        <add-one theme="outline" size="22" fill="#fff" />
        <!-- {{ item.title }} -->
        <el-popover
          placement="top-start"
          :title= "item.title"
          :width= "200"
          trigger="click"
          :content="item.content"
          
        >
          <template #reference>
            {{ item.title }}
          </template>
        </el-popover>
      </div>
      <div v-for="item in upData.fix" :key="item" class="uptext">
        <bug theme="outline" size="22" fill="#fff" />
        {{ item }}
      </div>
    </div>
  </el-card>
  <!-- </el-card> -->
</template>

<style lang="scss" scoped>
.update {
  margin-top: -15px;
  height: 100%;

  :deep(.el-card__body) {
    height: 100%;
  }
}
.title {
  display: flex;
  flex-direction: row;
  align-items: center;
  margin: 0.2rem 0 1.5rem;
  font-size: 1.1rem;
  .i-icon {
    display: flex;
    justify-content: center;
    align-items: center;
    margin-right: 6px;
  }
}
.upnote {
  // padding: 20px;
  padding-left: 20px;
  padding-top: 20px;
  height: calc(100%);
  overflow-y: auto;

  .uptext {
    display: flex;
    flex-direction: row;
    align-items: center;
    padding-bottom: 14px;
    font-size: 16px;

    &:nth-last-of-type(1) {
      padding: 0;
    }

    .i-icon {
      width: 22px;
      height: 22px;
      margin-right: 8px;
    }
  }
}

</style>

<script setup>

import { CloseOne, SettingTwo, GithubOne, AddOne, Bug , Tool, BackgroundColor} from "@icon-park/vue-next";
import { ElMessage } from "element-plus";

// 更新日志
// 修改为数组对象，以便于弹出明细日志
const upData = reactive({
new: [
    {"title": "部署最初版本主页", "content": "从github原代码fork出来，进行修改，部署到服务器，实现基本的功能。", key: 1},
    // {"title": "新增功能2", "content": "新增了一些功能22", key: 2}
],
fix: ["修复了一些bug"]
});

const showDetail = (item) => {
console.log(item.content);
    // 弹出明细气泡框

}
</script>
