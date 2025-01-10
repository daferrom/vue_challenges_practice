<!-- Vue.js provides a directive that renders the element and the component only once, and skips future updates. -->
<script setup>
import { ref } from "vue"

const count = ref(0)

setInterval(() => {
  count.value++
}, 1000)
</script>

<template>
  <span 
    v-once>Make it never change: {{ count }}
</span>
</template>

<!-- v-once es una directiva que permite asignar una propuiedad que solo se evalua una vez -->
<!-- con v-once el count no cambia de valor-->