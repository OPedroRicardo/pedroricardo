<template lang="pug">
q-layout
  router-view
</template>

<script>
export default ({
  name: 'MainLayout',

  data() {
    return {};
  },
});
</script>

<style lang="scss" scoped>
.q-layout {
  height: max-content;
  background-color: $dark;
}
</style>