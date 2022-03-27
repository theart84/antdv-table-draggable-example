<template>
  <draggable tag="tbody"
             :list="data"
             name="custom-table"
             @change="onChange"
             item-key="id"
             @start="dragging = true"
             @end="dragging = false">
    <template #item="{ element }">
      <tr class="ant-table-row ant-table-row-level-0">
        <td class="ant-table-cell">{{ element.id }}</td>
        <td class="ant-table-cell">{{ element.name }}</td>
        <td class="ant-table-cell">{{ element.email }}</td>
        <td class="ant-table-cell">{{ element.website }}</td>
      </tr>
    </template>
  </draggable>
</template>

<script lang="ts" setup>
import Draggable from 'vuedraggable';
import { ref } from 'vue';
import users from '../mock';

const data = ref(users);

const dragging = ref(false);

const onChange = (evt: any) => {
  console.log(evt.moved);
  console.log(JSON.parse(JSON.stringify(data.value)));
};

</script>
