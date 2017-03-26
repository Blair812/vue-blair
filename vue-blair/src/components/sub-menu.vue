<template>
<ul>
    <li v-for="m in model">  
        <div v-if="isFolder(m)" @click="toggle(m)" class="folder"><span><i></i>{{m.name}}</span><i class="after-span"></i></div>
        <span v-else><i></i>{{m.name}}</span>
		<sub-menu  v-show="m.open" :model="m.children"></sub-menu>
    </li>
</ul>

</template>

<script>
export default {
  name: 'subMenu',
  props: ['model'],
  data () {
    return {
    }
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
 ul{
 	margin:0px;
 	padding:0px;
 }
 li{
 	margin:0px;
 	padding:0px;
    list-style:none;
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
 li{
 	margin-left:14px;
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
