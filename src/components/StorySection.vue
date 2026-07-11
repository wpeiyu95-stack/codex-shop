<script setup>
const stats = [
  { value: "18", label: "个吧台座位" },
  { value: "42", label: "款小众酒单" },
  { value: "7", label: "天更新小菜单" },
];
</script>

<template>
  <section id="story" class="story">
    <div class="story-copy">
      <p class="eyebrow">Our Philosophy</p>
      <h2>少一点套路，多一点火候、香气和真实食材。</h2>
      <p>
        旬味不追求复杂摆盘，而是让每一道菜有明确的主角。开放厨房保留炭火、锅气和手工制作的过程，让用餐不只是吃完一道菜，而是看见它如何来到桌上。
      </p>
    </div>
    <div class="stats" aria-label="餐厅亮点">
      <div v-for="stat in stats" :key="stat.label">
        <strong>{{ stat.value }}</strong>
        <span>{{ stat.label }}</span>
      </div>
    </div>
  </section>
</template>
