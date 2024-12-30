<template>
<el-card class="update">
        <template #header>
        <div class="card-header">
            <span>更新日志</span>
        </div>
        </template>
        <div class="upnote">
        <div v-for="item in upData.new" :key="item" class="uptext">
            <add-one theme="outline" size="22" />
            {{ item }}
        </div>
        <div v-for="item in upData.fix" :key="item" class="uptext">
            <bug theme="outline" size="22" />
            {{ item }}
        </div>
        </div>
    </el-card>
</template>

<style lang="scss" scoped>
.update {
    margin-top: 30px;
    height: 100%;

    :deep(.el-card__body) {
        height: 100%;

        .upnote {
        padding: 20px;
        height: calc(100% - 56px);
        overflow-y: auto;

        .uptext {
            display: flex;
            flex-direction: row;
            align-items: center;
            padding-bottom: 16px;

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
    }
    }
</style>

<script setup>

import { CloseOne, SettingTwo, GithubOne, AddOne, Bug } from "@icon-park/vue-next";

// 更新日志
const upData = reactive({
new: ["部署最初版本主页"],
fix: ["修复了一些bug"]
});
</script>