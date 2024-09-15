<script>
import {reactive} from "vue"

export default {
  name: "App",
  components: {},
  data() {

    const initData = reactive({
      "theme": "light",
    })

    return {
      initData
    }

  }
}
</script>

<template>
  <RouterView :initData="initData" />
</template>

<style scoped>

</style>
