<script setup lang="ts">
// an defined interface that describes of each node on the tree
interface TreeData {
  key: string
  title: string
  children: TreeData[]
}
const props = defineProps<{ data: TreeData[] }>();

// Función para manejar la expansión y colapso de nodos
const toggleNode = (node: TreeData) => {
  node.expanded = !node.expanded;
};

</script>

<template>
    <div class="tree">
      <!-- Iteramos sobre cada nodo en data -->
      <ul>
        <li v-for="node in props.data"
            :key="node.key"
        >
          <!-- Botón para expandir o colapsar -->
          <button @click="toggleNode(node)">
            {{ node.expanded ? '[-]' : '[+]' }}
          </button>
          <!-- Título del nodo -->
          {{ node.title }}
          
          <!-- Si el nodo está expandido, mostramos sus hijos -->
          <ul v-if="node.expanded && node.children.length">
            <Tree
                :data="node.children"
            />
          </ul>
        </li>
      </ul>
    </div>
  </template>

<style scoped>
.tree ul {
  list-style-type: none;
  padding-left: 20px;
}

.tree button {
  margin-right: 10px;
  background-color: transparent;
  border: none;
  cursor: pointer;
}
</style>