<template>
  <component :is="tag" :class="size">
    <slot />
  </component>
</template>

<script>
export default {
  name: "CustomerText",
  props: {
    tag: {
      type: String,
      default: "span",
    },
    size: {
      type: String,
      default: "normal",
      validator: (value) => {
        return ["normal", "small", "xsmall", "xxsmall"].indexOf(value) !== -1;
      },
    },
  },
};
</script>

<style scoped>
.small {
  font-size: 12px;
}
.xsmall {
  font-size: 11px;
}
.xxsmall {
  font-size: 10px;
}
</style>
