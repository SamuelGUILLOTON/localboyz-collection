<script lang="ts">
import InstagramIcon from './icons/instagramIcon.vue';

export default {
    name: "Footer",
    components: { InstagramIcon }
}
</script>

<template>
  <div class="footer">
    <sub> Made by <a href="https://www.instagram.com/atticus_in_a_bluefunk/" target="_blank">Samuel Guilloton</a> with <strong>❤</strong></sub>
    <sub class="lcb-insta"> Suivez nous, c'est par ici : <a href="https://www.instagram.com/we_are_localboyz/" target="_blank"> <InstagramIcon/>  </a> </sub>
  </div>
</template>

<style scoped>
.footer {
    font-size: 12px;
    display: flex;
    justify-content: space-between;
}
.lcb-insta {
      display: flex;
}

.lcb-insta svg {
margin-left: 5px;
}
</style>
