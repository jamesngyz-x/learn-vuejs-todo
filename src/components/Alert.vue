<template>
  <div>
    <div class="alert" :class="mode" role="alert">
      <slot />
    </div>
  </div>
</template>

<script>
export default {
  name: "Alert",
  props: ["mode"],
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.primary {
  color: #084298;
  background-color: #cfe2ff;
  border-color: #b6d4fe;
}
.success {
  color: #0f5132;
  background-color: #d1e7dd;
  border-color: #badbcc;
}
.danger {
  color: #842029;
  background-color: #f8d7da;
  border-color: #f5c2c7;
}
</style>
