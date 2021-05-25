<template>
  <div class="wrapper" :size="size">
    <button v-bind="$attrs">
      <slot />
    </button>
  </div>
</template>

<script>
export default {
  inheritAttrs:false,
  setup(props,context) {
    const {size, ...rest} = context.attrs
    return {size,rest}
  }
}
</script>

<style lang="scss">
.wrapper {
  border: 1px solid red;
}
</style>











