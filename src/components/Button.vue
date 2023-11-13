<template>
  <button class="btn" :style="{ background: color }" @click="onClick()">
    {{ text }}
  </button>
</template>

<script>
export default {
  name: "button-comp",
  props: {
    text: String,
    color: String,
  },
  methods: {
    onClick() {
      this.$emit("show-form");
    },
  },
};
</script>
