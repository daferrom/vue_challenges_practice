<script setup>
defineProps({
  type: {
    type: String,
    default: "default",
    validator(value, props) {
        // The value must match one of these strings
        return ["primary", "ghost", "dashed", "link", "text", "default"].includes(value);
      }
  },
})
</script>

<template>
  <button>Button</button>
</template>

