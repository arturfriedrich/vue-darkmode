<script>
import { reactive } from "vue";
import HeaderComponent from "@/components/Header.vue";

export default {
  name: "App",
  components: { HeaderComponent },
  data() {
    const initData = reactive({
      theme: "light",
    });

    return {
      initData,
    };
  },
  methods: {
    toggleTheme() {
      this.initData.theme = this.initData.theme === "dark" ? "light" : "dark";
    },
  },
};
</script>

<template>
  <HeaderComponent :initData="initData" @toggleTheme="toggleTheme"/>
  <RouterView :initData="initData"/>
</template>

<style scoped>

</style>
