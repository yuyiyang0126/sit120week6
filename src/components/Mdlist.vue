<template>
<div class="root">
	<ul>
		<li>Modify List</li>
		<li v-for="(item,index) in list">{{index+1}}. {{item}}</li>
	</ul>
</div>	
</template>

<script>
export default{
	name:"Mdlist",
	data() {
		return {
			list:['Carbon spoiler','Carbon Lip','Carbon Windspliter','M4 conpetition wheel']
		}
	}
}	
</script>

<style scoped="scoped">
ul li{ line-height: 40px;}
</style>
