<script>
export default {
  name: "HeaderComponent",
  props: ["initData"],
  emits: ["toggleTheme"],
};
</script>

<template>
  <nav :class="['navbar', initData.theme === 'dark' ? 'navbar-dark bg-dark' : 'navbar-light bg-light']">
    <div class="container-fluid">
      <a class="navbar-brand" href="#">Artúr Friedrich</a>
      <div class="navbar-nav">
        <ul class="navbar-nav d-flex flex-row align-items-center">
          <li class="nav-item me-3">
            <span @click="$emit('toggleTheme')" style="cursor: pointer;">
              <i :class="[initData.theme === 'dark' ? 'fa-solid fa-lightbulb' : 'fa-solid fa-moon', 'fa-lg']"></i>
            </span>
          </li>
        </ul>
      </div>
    </div>
  </nav>
</template>

<style scoped>
.navbar-dark .fa-lightbulb {
  color: #ffffff;
}

.navbar-light .fa-moon {
  color: #000000;
}
</style>
