<template>
  <div class="advert container">
    <h2 ref="title" class="advert__title">
      <slot name="title"></slot>
    </h2>
    <slot></slot>
  </div>
</template>

<script>
export default {
  name: "advert",
  props: ["titleUpper"],
  mounted() {
    if (this.$props.titleUpper) {
      let title = this.$refs.title;
      title.innerHTML = title.innerHTML.toUpperCase();
    }
  }
};
</script>

<style lang="less" scoped>
.advert {
  padding: 53px 70px;

  background: var(--color-advert-bg);

  -webkit-box-shadow: 0px 0px 30px 0px rgba(0, 0, 0, 0.10);
  -moz-box-shadow: 0px 0px 30px 0px rgba(0, 0, 0, 0.10);
  box-shadow: 0px 0px 30px 0px rgba(0, 0, 0, 0.10);

  &__title {
    font-size: 36px;
    font-weight: 900;
    line-height: 50px;

    color: var(--color-font-light);

    margin-bottom: 40px;
  }
}
</style>
