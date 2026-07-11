<script setup>
import heroImage from "../../assets/restaurant-hero.png";
</script>

<template>
  <section id="home" class="hero" aria-label="餐厅主视觉">
    <img :src="heroImage" alt="温暖灯光下的现代餐厅餐桌与精致菜品" />
    <div class="hero-overlay"></div>
    <div class="hero-content">
      <p class="eyebrow">当季风味 · 开放厨房 · 晚餐与小酌</p>
      <h1>把今晚，留给一张热气腾腾的餐桌。</h1>
      <p class="hero-copy">旬味餐厅用本地食材、炭火香气和细腻酒单，做一顿轻松却值得记住的晚餐。</p>
      <div class="hero-actions">
        <a class="button button-primary" href="#booking">立即订位</a>
        <a class="button button-ghost" href="#menu">查看菜单</a>
      </div>
    </div>
    <aside class="hero-panel" aria-label="营业信息">
      <span>今日晚餐</span>
      <strong>17:30 - 22:30</strong>
      <small>周末建议提前预约</small>
    </aside>
  </section>
</template>
