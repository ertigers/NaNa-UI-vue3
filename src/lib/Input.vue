<template>
  <input class="nana-input" 
    :class="classes" 
    :type="type" 
    :clearable="clearable"
    :disabled="disabled" 
    :placeholder="placeholder">
</template>

<script>
import { computed } from 'vue';
export default {
  props: {
    size: {
      type: String,
      default: "normal",
    },
    radius: {
      type: String,
      default: "normal",
    },
    type: {
      type: String,
      default: "normal",
    },
    clearable: {
      type: String,
      default: "",
    },
    disabled: {
      type: Boolean,
      default: false,
    },
    placeholder: {
      type: String,
      default: "请输入~",
    }
  },
  setup(props) {
    const { size, radius } = props;
    const classes = computed(() => {
      return {
        [`nana-input-size-${size}`]: size,
        [`nana-input-radius-${radius}`]: radius,
      };
    });
    return { classes };
  },
}
</script>

<style lang="scss">
$grey: rgb(196, 196, 196);
.nana-input {
  border: 1px solid  $grey;
  padding: 10px 6px;
  border-radius: 4px;
  & + & {
    margin-left: 14px;
  }
  &:hover,
  &:focus {
    color: rgb(0, 0, 0);
    border-color: rgb(50, 171, 211);
  }
  &:focus {
    outline: none;
  }
  &::-moz-focus-inner {
    border: 0;
  }
  &.nana-input-size-small {
    padding: 8px 4px;
  }
  &.nana-input-size-big {
    padding: 14px 8px;

  }
}

</style>










