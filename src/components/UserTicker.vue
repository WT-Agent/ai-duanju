<template>
  <div class="glass-card ticker-card">
    <div class="ticker-wrapper">
      <div v-for="(item, index) in tickerItems" :key="index" class="ticker-item">
        <span>{{ item.text }}</span>
        <span style="color: var(--success-color); font-weight: bold;">[剧本策划完成]</span>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue';

const tickerItems = ref([
  { text: '用户 139****8821 成功生成 80集战神归来题材微短剧黄金前3秒与分集大纲' },
  { text: '用户 158****2204 策划了 抖音海外Shorts真假千金豪门逆袭爆点剧本与分镜提示' },
  { text: '用户 186****9012 完成了 微信小程序穿越古代搞科技 100集卡点留存钩子方案' },
  { text: '用户 135****4439 生成了 快手悬疑无限流死亡轮回短剧拍摄分镜与爆款金句' },
  { text: '用户 177****6618 策划了 3-5分钟精致甜宠战术契约霸总爽点反转剧本' },
]);
</script>
