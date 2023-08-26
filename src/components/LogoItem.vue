<template>
  <div class="logo">
    <img src="./Icons/LogoIcon.svg" alt="Logo" />
    PNFT Market
  </div>
</template>

<script>
export default {
  name: "LogoItem",
  props: {
    msg: String,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.logo {
  display: flex;
  align-items: center;
  gap: 12px;
}
</style>
