<template>
<div class="root">
	<v-header></v-header>
	

	<div class="subscribe">
		<div class="box">
			<div class="form">
				<dl><dt>Name</dt><dd><input type="text" ref="nameobj" v-model="name"></dd></dl>
				<dl><dt>Email</dt><dd><input type="text" ref="emailobj" v-model="email"></dd></dl>
				<dl><dt>Number</dt><dd><input type="text" ref='phoneobj' v-model="phone"></dd></dl>
			</div>
			<div class="desc">Complete the form to subscribe to my website</div>
		</div>
		<div class="btn"><a href="javascript:;" @click="subobj()">Submit</a></div>
	</div>
	
	
	<v-alert ref="alert" msg=''>
		<template><div class="t" slot="header">Thank you for Subscribing</div></template>
	</v-alert>

	
</div>	

</template>

<script>
import vHeader from '@/components/header.vue';
import vAlert from '@/components/Alert.vue';
export default {
	name:'Subscribe',
	data() {
		return {
			name:'',
			email:'',
			phone:''
		}
	},
	components:{
		vHeader,vAlert
	},
	methods:{
		subobj(){
			if(this.name==''){
				this.$refs.nameobj.style.border="1px solid red";
				return false;
			}else{
				this.$refs.nameobj.style.border="1px solid #ccc";
			}
			
			if(this.email==''){
				this.$refs.emailobj.style.border="1px solid red";
				return false;
			}else{
				this.$refs.emailobj.style.border="1px solid #ccc";
			}
			
			if(this.phone==''){
				this.$refs.phoneobj.style.border="1px solid red";
				return false;
			}else{
				this.$refs.phoneobj.style.border="1px solid #ccc";
			}
			this.name='';
			this.email='';
			this.phone='';
			this.$refs.alert.btnClose();
		}
	}
}
</script>

<style scoped="scoped">
	.subscribe{ width: 500px; height: auto; overflow: hidden; margin: 60px auto 0;background: #fff; padding:20px 0 0 20px; font-family: orbitron;}
	.subscribe .box{ display: flex; }
	.subscribe .form{width: 50%;}
	.subscribe .form dl{ margin-bottom: 10px;}
	.subscribe .form dl dt{ margin-bottom: 5px;}
	.subscribe .form input{width: 100%; border: 1px solid #ccc; height: 30px; text-indent: 5px;font-size: 16px;}
	.subscribe .desc{ display: flex; align-items: center; justify-content: center; padding-left: 20px;}
	.subscribe .btn{width: 100%; height: auto; overflow: hidden; text-align:right}
	.subscribe .btn a{width: 120px; height:35px; line-height: 35px; text-align: center; background: #3600ff; display: inline-block;}
</style>