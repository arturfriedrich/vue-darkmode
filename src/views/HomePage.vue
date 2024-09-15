<script>
export default {
  name: "HomePage",
  props: ["initData"],
  computed: {
    themeClass() {
      return this.initData.theme === "dark" ? "bg-dark text-light" : "bg-light text-dark";
    },
  },
};
</script>

<template>
  <div :class="themeClass" class="p-5" style="min-height: calc(100vh - 56px);">
    <div class="container">
      <div class="bento-grid">
        <div class="bento-item wide"></div>
        <div class="bento-item medium"></div>
        <div class="bento-item large"></div>
        <div class="bento-item small"></div>
        <div class="bento-item small"></div>
      </div>
    </div>
  </div>
</template>

<style scoped>
.bento-grid {
  display: grid;
  grid-template-columns: repeat(12, 1fr);
  grid-auto-rows: minmax(200px, auto);
  gap: 24px;
  width: 100%;
  height: 100%;
}

.bento-item {
  background-color: #e0e0e0;
  border-radius: 12px;
  box-shadow: 5px 5px 10px #bebebe, -5px -5px 10px #ffffff;
  transition: box-shadow 0.3s ease;
}

.bento-item:hover {
  box-shadow: 2px 2px 5px #bebebe, -2px -2px 5px #ffffff;
}

.bento-item.large {
  grid-column: span 8;
  grid-row: span 2;
}

.bento-item.medium {
  grid-column: span 4;
  grid-row: span 1;
}

.bento-item.small {
  grid-column: span 2;
  grid-row: span 1;
}

.bento-item.wide {
  grid-column: span 12;
  grid-row: span 1;
}

.bg-dark .bento-item {
  background-color: #2e2e2e;
  box-shadow: 5px 5px 10px #1c1c1c, -5px -5px 10px #3a3a3a;
}

.bg-light .bento-item {
  background-color: #e0e0e0;
  box-shadow: 5px 5px 10px #bebebe, -5px -5px 10px #ffffff;
}
</style>
