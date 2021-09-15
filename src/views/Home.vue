<template>
<div class="home">
	<v-header></v-header>
	
	<div class="main">
		<div class="hello">Hello,It's</div>
		<div class="username">Eric Yu</div>
		<div class="love">
			<p>An Car enthusiast who likes to</p>
			<ul><li v-for="(item,index) in loveArr">{{index+1}}. {{item}}</li></ul>
		</div>
		<div class="read">
			<div class="btn"><a href="javascript:;" @click="showRead()">Click Here to read more</a></div>
			<div class="more" v-if="show">
				<p>I am currently an undergraduate student studying information Technology at Deakin University</p>
			</div>
		</div>
	</div>
</div>
</template>

<script>
import vHeader from '@/components/header.vue';
export default {
  name: 'Home',
  data() {
	return {
		show:false,
		loveArr:['Photograph','Programing','Gaming']
	}
  },
  components:{
	vHeader
  },
  methods:{
	showRead(){
		this.show=!this.show;
	}
  }
}
</script>

<style type="text/css" scoped="scoped">
.main{width: 100%;  color: #fff; padding: 20px; background: url(../assets/img/home.png) no-repeat right 20px top 20px;}
.main .hello{ font-size: 60px;}
.main .username{font-size: 60px; text-indent: 100px;}
.main .love{ padding-top:40px;}
.main .love p{ padding: 10px 0;}
.main .love ul li{ line-height: 2; }
.main .read .btn { width: 100%; height: auto; overflow: hidden; padding: 20px 0; font-family: Orbitron; }
.main .read .btn a{ color:blue; display: block; width: auto; padding: 5px 10px; border: 2px solid blue; float: left;}
</style>
