<template>
  <div class="sidebar">
    <el-button @click="sidebarFold = !sidebarFold">展开/折叠</el-button>
    <el-menu
      :default-active="'home-1'"
      :collapse="sidebarFold"
      background-color="#545c64"
      text-color="#fff"
      active-text-color="#ffd04b"
    >
      <sidebar-item v-for="menu in menuList" :key="menu.menuId" :menu="menu"></sidebar-item>
    </el-menu>
  </div>
</template>
<script>
import sidebarItem from './sidebar-item'
export default {
  name: 'sidebar',
  components: {
    sidebarItem
  },
  data() {
    return {
      sidebarFold: false, // 控制菜单的折叠和展开
      menuList: [
        {
          icon: 'el-icon-menu',
          menuId: 'home',
          name: '首页',
          list: [
            {
              icon: 'el-icon-menu',
              menuId: 'home-1',
              name: '首页一'
            },
            {
              icon: 'el-icon-menu',
              menuId: 'home-2',
              name: '首页二'
            },
            {
              icon: 'el-icon-menu',
              menuId: 'home-3',
              name: '首页三',
              list: [
                {
                  icon: 'el-icon-menu',
                  menuId: 'home-3-1',
                  name: '首页三-1'
                }
              ]
            }
          ]
        },
        {
          icon: 'el-icon-document',
          menuId: 'photo',
          name: '相册',
          list: null
        },
        {
          icon: 'el-icon-setting',
          menuId: 'blog',
          name: '博客',
          list: null
        },
        {
          icon: 'el-icon-location',
          menId: 'news',
          name: '新闻',
          list: null
        }
      ]
    }
  }
}
</script>
<style scoped>
.sidebar {
  width: 220px;
}
</style>