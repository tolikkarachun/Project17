<template>
  <div class="copyright">@CreatedbyNAMDesign</div>
</template>

<script>
export default {
  name: "CopyRight",
  props: {
    msg: String,
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
.copyright {
  color: #667085;
  font-family: Inter;
  font-size: 16px;
  font-style: italic;
  font-weight: 400;
  line-height: 20px;
}
</style>
