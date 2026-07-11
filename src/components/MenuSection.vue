<script setup>
const menuItems = [
  { name: "炭烤海鲈鱼", description: "柠檬百里香、烤甜椒汁、脆皮土豆。", price: "68元" },
  { name: "慢炖牛颊肉", description: "红酒汁、焦化洋葱泥、时令根茎蔬菜。", price: "¥188", featured: true },
  { name: "手工野菌宽面", description: "榛子黄油、帕玛森、黑胡椒和新鲜香草。", price: "¥118" },
];
</script>

<template>
  <section id="menu" class="menu-section">
    <div class="section-heading">
      <p class="eyebrow">Seasonal Menu</p>
      <h2>本周精选</h2>
    </div>
    <div class="menu-grid">
      <article
        v-for="(item, index) in menuItems"
        :key="item.name"
        class="menu-item"
        :class="{ featured: item.featured }"
      >
        <span class="menu-index">{{ String(index + 1).padStart(2, "0") }}</span>
        <h3>{{ item.name }}</h3>
        <p>{{ item.description }}</p>
        <strong>{{ item.price }}</strong>
      </article>
    </div>
  </section>
</template>
