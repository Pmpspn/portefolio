<template>
  <div class="wrapper">
    <div class="home h-screen">
      <Content/>
    </div>
    <div class="left h-screen"></div>
    <div class="right h-screen"></div>
  </div>
</template>

<script>

import Content from './Content.vue'

export default {
  name: "Home",
  components: {
    Content
  },
}
</script>

<style scoped>
.wrapper {
  display: grid;
  grid-template-columns: 1fr 1fr;
}

.home {
  grid-column: 1/3;
  background-color: #121719;
}

.left {
  grid-column: 1/1;
  background-color: #13191C;
}

.right {
  grid-column: 2/2;
  background-color: #161E22;
}
</style>