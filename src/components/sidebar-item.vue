<template>
<div>
  <el-submenu
    v-if="menu.list && menu.list.length >= 1"
    :index="menu.menuId + ''"
  >
    <template slot="title">
      <i :class="menu.icon"></i>
      <span>{{ menu.name }}</span>
    </template>
    <sidebar-item v-for="item in menu.list" :key="item.menuId" :menu="item"></sidebar-item>
  </el-submenu>
  <el-menu-item v-else :index="menu.menuId + ''">
    <i :class="menu.icon"></i>
    <span>{{ menu.name }}</span>
  </el-menu-item>
  </div>
</template>
<script>
export default {
  name: "sidebar-item",
  props: {
    menu: {
      type: Object,
      required: true
    }
  },
  methods: {}
};
</script>