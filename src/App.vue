<template>
  <div class="sing-in">
    <div class="sing-in__info">
      <LogoItem />
      <FormItem />
      <CopyrightItem />
    </div>
    <div class="sing-in__bg">
      <BgImg />
    </div>
  </div>
</template>

<script>
import BgImg from "./components/BgImg.vue";
import LogoItem from "./components/LogoItem.vue";
import FormItem from "./components/FormItem.vue";
import CopyrightItem from "./components/CopyrightItem.vue";

export default {
  name: "App",
  components: {
    BgImg,
    LogoItem,
    FormItem,
    CopyrightItem,
  },
};
</script>

<style>
* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
  font-family: "Inter", sans-serif;
}
img {
  height: 100%;
}

a {
  text-decoration: none;
}

li {
  list-style: none;
}
.sing-in {
  padding: 32px;
  position: fixed;
  width: 100%;
  height: 100%;
  display: flex;
  justify-content: space-between;
  gap: 20px;
}

.sing-in__info {
  flex-grow: 1;
  flex-shrink: 0;
  display: grid;
  grid-template-rows: auto 1fr auto;
}

.sing-in__bg {
  flex: 0 1 768px;
}

</style>
