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
      <a class="navbar-brand" href="#">MyApp</a>
      <div class="navbar-nav">
        <ul class="navbar-nav d-flex flex-row align-items-center">
          <li class="nav-item me-3">
            <a class="nav-link active" aria-current="page" href="#">Home</a>
          </li>
          <li class="nav-item me-3">
            <a class="nav-link" href="#">Features</a>
          </li>
          <li class="nav-item me-3">
            <a class="nav-link" href="#">Pricing</a>
          </li>
          <!-- Theme switcher button -->
          <li class="nav-item me-3">
            <button class="btn btn-outline-primary" @click="$emit('toggleTheme')">
              Switch to {{ initData.theme === "dark" ? "Light" : "Dark" }} Mode
            </button>
          </li>
        </ul>
      </div>
    </div>
  </nav>
</template>

<style scoped>
</style>
