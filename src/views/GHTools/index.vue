<template>
  <div class="box cards" @mouseenter="closeShow = true" @mouseleave="closeShow = false">
    
    
    <el-tabs type="border-card" class="cards tabs custom-tabs">
    <el-tab-pane label="文本批量替换">User</el-tab-pane>
    <el-tab-pane label="颜色调整器">Config</el-tab-pane>
    <el-tab-pane label="其他功能">开发中</el-tab-pane>
  </el-tabs>

  <transition name="el-fade-in-linear">
      <close-one
        class="close"
        theme="filled"
        size="28"
        fill="#ffffff60"
        v-show="closeShow"
        @click="store.toolsOpen = false"
      />
    </transition>
  </div>

</template>

<script setup>
import { CloseOne, SettingTwo } from "@icon-park/vue-next";
import { mainStore } from "@/store";
import { ElTabs, ElTabPane } from "element-plus";

const store = mainStore();
const closeShow = ref(false);
</script>

<style lang="scss" scoped>
.box {
  flex: 1 0 0%;
  // margin-left: 0.75rem;
  height: 90%;
  width: 90%;
  // max-width: 95%;
  position: relative;
  animation: fade 0.5s;

  &:hover {
    transform: scale(1);
  }

  .close,
  .setting {
    position: absolute;
    top: 14px;
    right: 14px;
    width: 28px;
    height: 28px;
    transition:
      transform 0.3s,
      opacity 0.3s;

    &:hover {
      transform: scale(1.2);
    }

    &:active {
      transform: scale(1);
    }
  }

  .setting {
    right: 56px;
  }

  .content {
    display: flex;
    flex-direction: column;
    padding: 30px;
    width: 100%;
    height: 100%;
  }
}
.tabs {
  flex: 1 0 0%;
  height: 100%;
  // max-width: 95%;
  position: relative;
  animation: fade 0.5s;

  &:hover {
    transform: scale(1);
  }
}

.custom-tabs {
  background-color: transparent !important;
  border: none;
  :deep(.el-tabs__header){
    background-color: transparent !important;
    border: none;
  }
  :deep(.el-tabs__content){
    background-color: transparent !important;
  }
  :deep(.el-tabs_pane){
    background-color: transparent !important;
  }
}

</style>
