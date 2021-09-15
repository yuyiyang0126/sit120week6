<template>
<div class="root">
	<div class="header">
		<div class="nav">
			<ul>
				<li><a href="/">Home</a></li>
				<li>|</li>
				<li><router-link to="/mycar">Mycar</router-link></li>
				<li>|</li>
				<li><router-link to="/checklist">Checklist</router-link></li>
				<li>|</li>
			</ul>
		</div>
		<div class="music">
			<ul>
				<li><a href="javascript:;" @click="play()">{{playText}}</a></li>
				<li><router-link to="/Subscribe">Subscribe</router-link></li>
			</ul>
		</div>
	</div>
	
	<audio src="../assets/music/v.mp3" ref="music"></audio>
</div>
</template>

<script>
export default{
	name:'Header',
	data() {
		return {
			playText:'Play'
		}
	},
	methods:{
		play(){
			var obj=this.$refs.music;
			if(obj.paused){
			    obj.play();
				this.playText="Pause";
			}else{
			    obj.pause();
					this.playText="Play";
			}
		}
	}
}	
</script>

<style>
.header{width: 100%; height: 60px; background: #fff; display: flex; justify-content: space-between; align-items: center; position: fixed; top:0;}
.header .nav ul{display:flex; align-items: center; padding-left: 20px;font-family: Orbitron;}
.header .nav ul li:nth-child(2n){ padding: 0 20px;}
.header .nav ul li a{font-size: 18px;}
.header .nav ul li a:hover{ color: #ff0000;}
.header .music ul{display: flex; font-size: 16px;}
.header .music ul li a{width: 130px; height: 60px; line-height: 60px; display: block; text-align: center;}
.header .music ul li:first-child a{background: #ff0000; opacity: 0.8;display: inline-block; transition: 0.2s;color:black; font-family:Orbitron;}
.header .music ul li:last-child a{background: #3a00f3;opacity: 0.8; transition: 0.2s;display: inline-block; color:black;font-family:Orbitron;}
.header .music ul li:first-child a:hover {opacity: 1}
.header .music ul li:last-child a:hover {opacity: 1}
@media(max-width:768px){
	.header .nav ul{ padding-left: 10px;}
	.header .nav ul li:nth-child(2n){ padding: 0 6px;}
	.header .nav ul li a{font-size: 14px;}
	.header .music ul{font-size: 14px;}
	.header .music ul li a{width: 60px; height: 30px; line-height: 30px;}
}
</style>
