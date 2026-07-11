<script setup>
import { nextTick, onBeforeUnmount, onMounted, ref } from "vue";

const navItems = [
  { href: "#menu", label: "菜单" },
  { href: "#story", label: "理念" },
  { href: "#space", label: "环境" },
  { href: "#booking", label: "订位" },
];

const isMenuOpen = ref(false);
const isScrolled = ref(false);
const activeSection = ref("");
let observer;

function updateHeader() {
  isScrolled.value = window.scrollY > 16;
}

function toggleMenu() {
  isMenuOpen.value = !isMenuOpen.value;
}

function closeMenu() {
  isMenuOpen.value = false;
}

onMounted(async () => {
  window.addEventListener("scroll", updateHeader, { passive: true });
  updateHeader();
  await nextTick();

  observer = new IntersectionObserver(
    (entries) => {
      entries.forEach((entry) => {
        if (entry.isIntersecting) activeSection.value = entry.target.id;
      });
    },
    { rootMargin: "-42% 0px -48% 0px", threshold: 0 },
  );

  navItems.forEach(({ href }) => {
    const section = document.querySelector(href);
    if (section) observer.observe(section);
  });
});

onBeforeUnmount(() => {
  window.removeEventListener("scroll", updateHeader);
  observer?.disconnect();
});
</script>

<template>
  <header class="site-header" :class="{ 'is-scrolled': isScrolled }">
    <a class="brand" href="#home" aria-label="旬味餐厅首页" @click="closeMenu">
      <span class="brand-mark">旬</span>
      <span>
        <strong>旬味餐厅</strong>
        <small>Seasonal Table</small>
      </span>
    </a>

    <nav class="site-nav" :class="{ 'is-open': isMenuOpen }" aria-label="主导航">
      <a
        v-for="item in navItems"
        :key="item.href"
        :href="item.href"
        :class="{ 'is-active': activeSection === item.href.slice(1) }"
        @click="closeMenu"
      >
        {{ item.label }}
      </a>
    </nav>

    <button
      class="nav-toggle"
      type="button"
      :aria-label="isMenuOpen ? '关闭导航' : '打开导航'"
      :aria-expanded="isMenuOpen"
      @click="toggleMenu"
    >
      <span></span>
      <span></span>
    </button>
  </header>
</template>
