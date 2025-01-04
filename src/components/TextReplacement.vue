<template>
    <div class="TextReplacement">
        <el-input
            v-model="textAreaInput"
            type="textarea"
            placeholder="Please input"
            class="inputText"
        />
    </div>
</template>

<script setup>

import { ElText, ElInput } from 'element-plus';

</script>

<style lang="scss" scoped>

.inputText{
    width: 80%;
    padding:5%;
    :deep(.el-textarea__inner){
        background-color: #ffffff30;
        border: none;
    }
}

</style>