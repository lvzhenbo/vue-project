<script setup lang="ts">
import { reactive } from 'vue';
import MyInput from './MyInput.vue';

// 非 Ref 的绑定：模板里会被生成成 `state.value.text`，
// 依赖 __VLS_template 顶部的 __VLS_withDotValue(state, ...) 断言补出 `.value`。
const state = reactive({ text: '' });
</script>

<template>
  <!-- 属性值里的 `//` 会被 props 拷贝的转义逻辑破坏成非法代码 -->
  <MyInput v-model="state.text" placeholder="http://127.0.0.1:7890" />
</template>

<style scoped></style>
