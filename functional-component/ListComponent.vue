<script setup lang='js'>

  defineProps({
  list: Array,
  activeIndex: Number
});
  const emit = defineEmits("tLIst")

  function emitToggle(index){
    emit('toggle', index)
  }
</script>

<template>
  <ul>
    <li 
      v-for="item, index in list"
      @click="emitToggle(index)"
    >
      {{item.name}}
    </li>
  </ul>
</template>
