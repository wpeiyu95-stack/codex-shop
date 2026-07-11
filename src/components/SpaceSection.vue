<script setup>
const spaces = [
  { name: "开放厨房", className: "large" },
  { name: "吧台小酌", className: "warm" },
  { name: "半开放包间", className: "green" },
];
</script>

<template>
  <section id="space" class="space">
    <div class="section-heading">
      <p class="eyebrow">Dining Room</p>
      <h2>适合把时间慢下来的空间</h2>
    </div>
    <div class="space-grid">
      <div v-for="space in spaces" :key="space.name" class="space-shot" :class="space.className">
        <span>{{ space.name }}</span>
      </div>
    </div>
  </section>
</template>
