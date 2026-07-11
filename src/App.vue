<script setup>
import BookingSection from "./components/BookingSection.vue";
import HeroSection from "./components/HeroSection.vue";
import MenuSection from "./components/MenuSection.vue";
import SiteFooter from "./components/SiteFooter.vue";
import SiteHeader from "./components/SiteHeader.vue";
import SpaceSection from "./components/SpaceSection.vue";
import StorySection from "./components/StorySection.vue";
</script>

<template>
  <SiteHeader />
  <main>
    <HeroSection />

    <section class="intro">
      <div>
        <p class="eyebrow">Chef's Note</p>
        <h2>餐盘要有季节感，也要有回家的松弛感。</h2>
      </div>
      <p>
        我们每天根据市场到货调整小菜单：海鲜、蔬菜、香草和发酵调味都保留清晰层次。服务节奏不催促，适合约会、朋友聚餐，也适合一个人坐在吧台慢慢吃。
      </p>
    </section>

    <MenuSection />
    <StorySection />
    <SpaceSection />
    <BookingSection />
  </main>
  <SiteFooter />
</template>
