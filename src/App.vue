<template>
  <a-layout class="layout">
    <a-layout-header>
      <h2 style="color: white">Ant Design Vue 3 Draggable Table Example</h2>
    </a-layout-header>
    <a-layout-content style="padding: 0 50px">
      <div :style="{ background: '#fff', padding: '24px', minHeight: '280px' }">
        <a-table
          :columns="columns"
          :components="components"
        />
      </div>
    </a-layout-content>
  </a-layout>
</template>

<script lang="ts" setup>
import DraggableBodyWrapper from './components/DraggableBodyWrapper.vue';

const columns = [
  {
    title: 'ID',
    dataIndex: 'id',
    key: 'id',
  },
  {
    title: 'Name',
    dataIndex: 'name',
    key: 'name',
  },
  {
    title: 'Email',
    dataIndex: 'email',
    key: 'email',
  },
  {
    title: 'Website',
    dataIndex: 'website',
    key: 'website',
  },
];

const components = {
  body: {
    wrapper: DraggableBodyWrapper,
  },
};
</script>
