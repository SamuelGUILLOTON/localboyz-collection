<template>
  <div class="head">
    <h1 class="title-logo">
      <RouterLink to="/">
        <span class="first-letter">L</span>ocal <span class="first-letter">B</span>oyz
        <span class="first-letter">C</span>ollections</RouterLink>
    </h1>
    <p>Retrouves ici, tout les clips réalisés par nos soins</p>
  </div>
  <router-view />
</template>

<script lang="ts">
export default {
  name: 'Navbar'
}
</script>
<style lang="less" scoped>
.head {
  h1 {
    color: #dacfcf;
    text-align: center;
  }
}
#app {
  .nav-list.green.disabled {
    display: none;
  }
}
</style>
