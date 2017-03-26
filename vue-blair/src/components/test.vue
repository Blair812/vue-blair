<template>
  <div style="width:200px;background-color:#ffffff;">
    
    <tree-menu :list="list"></tree-menu>
      
  </div>
</template>

<script>
import treeMenu from './menu'
export default {
  name: 'menu',
  data () {
    return {
      open: false,
      isFolder: false,
      list: [{
        name: '一级菜单1',
        children: []
      },
      {
        name: '一级菜单2',
        children: [{
          name: '二级菜单1',
          children: [{
            name: '三级菜单1',
            children: []
          }]
        },
        {
          name: '二级菜单2',
          children: []
        }]
      }]
    }
  },
  components: {
    treeMenu
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
 
</style>
