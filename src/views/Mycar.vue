<template>
<div class="root">
	<v-header></v-header>
	
	<div class="mycar">
		<div class="top">
			<div class="info">
				<h2>This is my car 2014 BMW M4</h2>
				<div class="item">
					<v-mdlist></v-mdlist>
				</div>
			</div>
			<div class="thumb">
				<div class="pic"><img src="@/assets/img/img01.png" alt=""></div>
				<div class="btn">
					<ul>
						<li v-for="(item,index) in msgArr">{{item}}</li>
					</ul>
				</div>
			</div>
		</div>
		
		<div class="form">
			<p>Tell me what you think of my car</p>
			<div class="box">
				<textarea rows="" cols="" v-model="message" ref="message"></textarea>
				<button @click="showModel()">Submit</button>
			</div>
		</div>
	</div>
	
	<div class="showModel" v-show="show">
		<div class="btn"><a href="javascript:;" @click="showModel(1)">×</a></div>
		<div class="info">Thank you for your support</div>
	</div>
</div>	
</template>

<script>
import vHeader from '@/components/header.vue';
import vMdlist from '@/components/Mdlist.vue';
export default{
	data() {
		return {
			show:false,
			message:'',
			msgArr:[],
		}
	},
	components:{
		vHeader,vMdlist
	},
	methods:{
		showModel(flag){
			if(!flag){
				if(this.message==''){
					this.$refs.message.style.border='1px solid red';
					return false;
				}
				
				this.$refs.message.style.border='none';
				this.msgArr.push(this.message);
				this.message='';
			}
			
			this.show=!this.show;
		}
	}
}
</script>

<style scoped="scoped">
.mycar{ color:#fff; padding: 20px;}
.mycar .top{display: flex; justify-content: space-between; flex-wrap: wrap;}
.mycar .top .info .item{margin: 30px 0;}
.mycar .top .thumb .pic img{display: block; border: 1px solid #ccc; max-width: 100%;}
.mycar .top .thumb .btn{ margin-top: 30px;}
.mycar .top .thumb .btn ul li{display:inline-block; width:auto; height: 40px; line-height: 40px; padding: 0 10px; text-align: center; color: #fff; background: red;
}
.mycar .top .thumb .btn ul li:nth-child(2n){background: #3a00f3;}
.mycar .form p{ margin-bottom: 10px;} 
.mycar .form .box{display:flex; align-items: flex-end; }
.mycar .form textarea{width: 450px; height:200px; padding: 10px; font-size: 20px; font-family: oswald;}
.mycar .form button{width: 100px; height:30px; background: #3a00f3; color: black; cursor: pointer;font-size: 16px; font-family: orbitron;}
.showModel{width: 300px; background: #fee3e3; position: fixed; top: 50%; left: 50%; transform: translate(-50%,-50%);}
.showModel .btn a{ font-size: 20px; float: right; width: 20px; height: 20px; border-radius: 100%; background: red; text-align: center; line-height: 20px; color: #fff;}
.showModel .info{ padding:30px 20px; text-align: center;}
@media(max-width:768px){
	.mycar .top{ margin-bottom: 30px;}
}
</style>

