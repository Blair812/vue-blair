<template>
  <div style="width:200px;background-color:yellow;">
    <ul>
      <li v-for="item in list" class="li-level-first " :class="item.children.length?'li-border ':''">
        <span><i></i>{{item.name}}</span>
        <sub-menu v-if="item.children.length" :model="item.children"></sub-menu>
      </li>      
    </ul>   
      
  </div>
</template>

<script>
import subMenu from './sub-menu'
export default {
  name: 'menu',
  data () {
    return {
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
    subMenu
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
 ul{
  padding:0px;
  user-select:none;
 }

 ul li>ul{    
    list-style:none;
    
 }
 li.li-border:hover{
    border-left:1px solid blue;
 }

 li{
  list-style:none;
  padding:0px;
  margin:0px;
  line-height:40px;

 }
 li:hover{
  background-color:#666;
 }
 li.li-level-first{
  padding-left:24px;
 }
 i{
    width:18px;
    height:18px;
    vertical-align:middle;
    display:inline-block;    
    border:none;
    background-color:gray;
    margin-right:16px;
 }
</style>
