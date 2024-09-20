<template>
  <view class="container">
    <view class="background-overlay"></view>
    <!-- 背景叠加效果 -->
    <view class="welcome-text">
      <text style="font-size: 2.5rem">欢迎进入</text>
      <text class="welcome-text-right">赛斯检测站助手</text>
    </view>
    <view class="car_bg">
      <image src="../../static/car.png" mode="scaleToFill" class="car_bg_img" />
    </view>
    <view class="selection-buttons">
      <view>
        <button class="select-button company">进入</button>
      </view>
    </view>
  </view>
</template>

<script lang="ts" setup>
import { ref, onMounted } from 'vue'
import { onLoad } from '@dcloudio/uni-app'

const list = ref()
async function getTyoe() {}
const selectRole = (role: string) => {}
onLoad(() => {})
onMounted(() => {})
</script>

<style scoped>
/* 禁止滑动 */
html,
body,
.container {
  overflow: hidden; /* 禁止滚动条 */
  touch-action: none; /* 禁止触摸滑动 */
}

/* 主体背景和布局 */
.container {
  display: flex;
  flex-direction: column;
  /* justify-content: center; */
  justify-content: space-between;
  align-items: center;
  height: 100vh;
  background: linear-gradient(135deg, #6370fc, #a3d0f9); /* 青春活力渐变背景 */
  position: relative;
  overflow: hidden;
  text-align: center;
}

/* 添加背景装饰图片 */
.background-overlay {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-size: cover;
  opacity: 0.15;
  z-index: 0;
}

/* 文字样式 */
.welcome-text {
  margin-top: 3rem;
  display: flex;
  flex-direction: column;
  align-items: start;
  width: 100%;
  padding: 3rem 0 0 2.5rem;
  z-index: 1;
}

.welcome-text-right {
  text-align: center;
  display: block;
  width: 100%;
}

.welcome-text text {
  font-size: 28px;
  font-weight: bold;
  color: #fff;
  margin-bottom: 10px;
}
.car_bg {
  width: 600rpx;
  height: 420rpx;
  /* background-image: url('../../static/car_bg.png'); */
}
.car_bg_img {
  width: 600rpx;
  height: 420rpx;
}

.subtitle {
  font-size: 18px;
  color: #f5f6fa;
  margin-bottom: 50px;
}

/* 按钮样式 */
.selection-buttons {
  width: 100%;
  display: flex;
  flex-direction: column;
  gap: 20px;
  flex: 1;
  align-items: center;
  justify-content: center;
}

.select-button {
  width: 220px;
  padding: 14px;
  border-radius: 30rpx;
  color: white;
  font-size: 18px;
  font-weight: 500;
  transition: all 0.3s ease;
  cursor: pointer;
  border: none;
  z-index: 1;
  position: relative;
  background-size: cover;
  background-position: center;
  overflow: hidden;
}

/* 按钮悬停效果 */
.select-button:hover::before {
  content: '';
  position: absolute;
  top: -50px;
  left: 0;
  width: 100%;
  height: 200%;
  background: rgba(255, 255, 255, 0.1);
  transform: rotate(45deg);
  transition: all 0.3s ease-in-out;
}

.select-button:hover {
  box-shadow: 0 10px 20px rgba(0, 0, 0, 0.3);
}

/* 不同按钮的配色 */
.company {
  background: linear-gradient(135deg, #3331f9, #5e89fa); /* 企业人员按钮的渐变背景 */
  box-shadow: 10px 12px 4px 0px rgba(0, 0, 0, 0.1);
  margin-bottom: 1rem;
}

/* 高科技感动态线条背景 */
.container::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-size: cover;
  z-index: 0;
  opacity: 0.2;
}

/* 光晕效果 */
.container::after {
  content: '';
  position: absolute;
  top: 0;
  left: 50%;
  width: 200px;
  height: 200px;
  background: radial-gradient(circle, rgba(255, 255, 255, 0.5), transparent);
  border-radius: 50%;
  z-index: 0;
  animation: glow 5s infinite alternate;
}

@keyframes glow {
  from {
    transform: scale(1);
    opacity: 0.5;
  }
  to {
    transform: scale(1.5);
    opacity: 1;
  }
}
</style>
