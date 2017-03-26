<template>
<ul>
    <li v-for="m in model">  		    
     <span><i></i>{{m.name}}</span>
		 <sub-menu v-if="m.children.length > 0" :model="m.children"></sub-menu>
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
    background-color:gray;
    margin-right:16px;
 }
 li{
 	margin-left:14px;
 }
</style>
