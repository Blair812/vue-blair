<template>
  <div class="menu-con">
    <ul>
      <li v-for="item in list" class="li-level-first " :class="isFolder(item) && item.open?'li-border ':''">
        <div v-if="isFolder(item)" @click="toggle(item)" class="folder"><span><i></i>{{item.name}}</span><i class="after-span"></i></div>
        <span v-else><i></i>{{item.name}}</span>
        <sub-menu v-show="item.open" :model="item.children"></sub-menu>
      </li>      
    </ul>   
      
  </div>
</template>

<script>
import subMenu from './sub-menu'
export default {
  name: 'menu',
  props: ['list'],
  data () {
    return {
    }
  },
  components: {
    subMenu
  },
  methods: {
    toggle: function (it) {
      it.open = !it.open
    },
    isFolder: function (it) {
      return it.children && it.children.length
    }
  }

}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
 .menu-con{
  background-color:#ffffff;
 }
 ul{
  padding:0px;
  user-select:none;
 }

 ul li>ul{    
    list-style:none;
    
 }
 li.li-border{
    padding-left:20px;
    border-left:4px solid #4775b3;    
 }

 li{
  list-style:none;
  padding:0px;
  margin:0px;
  line-height:40px;

 }
  span{
    line-height:40px;
    display:inline-block;
  }

 li:hover{
  background-color:#edf3f9;
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
    background-color:#e2cbce;
    margin-right:16px;
 }
 .folder{
     position:relative;
     padding:0px;
 }
 .after-span{
     position:absolute;
     right:0px;
     top:10px;
 }
</style>
