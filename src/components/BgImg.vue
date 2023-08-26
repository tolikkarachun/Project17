<template>
  <div class="bgimg">
    <img alt="Bg Img" src="@/assets/bg.png">
  </div>
</template>

<script>
export default {
  name: 'BgImg',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.bgimg {
  height: 100%;
}
</style>
