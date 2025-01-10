<script setup lang='js'>
import ListComponent from "./ListComponent.vue";
import {ref, reactive} from "vue";

/**
 * Implement a functional component :
 * 1. Render the list elements (ul/li) with the list data
 * 2. Change the list item text color to red when clicked.
*/


const list = reactive([{
  name: "John",
}, {
  name: "Doe",
}, {
  name: "Smith",
}])

const activeIndex = ref(0)

function toggle(index) {
  activeIndex.value = index
}

</script>

<template>
  <list-component
    :list="list"
    :active-index="activeIndex"
    @toggle="toggle"
  />
</template>
